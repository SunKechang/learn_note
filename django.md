### django无法添加外键

报错：

> You are trying to add a non-nullable field 'subject_id' to tutor without a default; we can't do that (the database needs something to populate existing rows).

即目前存在的记录中没有这一列，所以django为了防止添加这一列后原来的数据存在缺失不让用户添加，可以在添加的一列中添加

```python
null=True
```

即允许该列为空，启用makemigrations命令生成sql语句，去掉null=True，再次执行makemigrations，此时选择2：

> Ignore for now, and let me handle existing rows with NULL myself (e.g. because you added a RunPython or RunSQL operation to handle NULL values in a previous data migration)

即可，然后运行migrate命令即可更新数据库中表

### django将两个字段设为联合主键

```python
class StudentProject(models.Model):
    stu_sno = models.ForeignKey(Student, on_delete=models.CASCADE, unique=False, verbose_name="研究生学号")
    attend_time = models.CharField(max_length=40, verbose_name="参与时间")
    work = models.CharField(max_length=40, verbose_name="承担工作")
    money = models.DecimalField(max_digits=20, decimal_places=1, verbose_name="折合经费（万）")
    project_id = models.ForeignKey(Project, on_delete=models.CASCADE, unique=False, verbose_name="项目编号")

    class Meta:
        constraints = [models.UniqueConstraint(fields=['stu_sno', 'project_id'], name='unique_project_log')]
```

class Meta中设定stu_sno和project_id两者共同为唯一的（unique不知道是不是需要）

### django模板语法（js中获取后端传入数据）

假设后端传入一个名为submittedActivities的数组变量，可以在js中使用

```django
{% for submittedActivity in submittedActivities %}
        console.log("{{submittedActivity.id}}")
    {% endfor %}
```

来循环submittedActivities获取其中的值
