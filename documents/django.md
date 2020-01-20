
## Django Admin

### 作成したモデルをadminに表示する方法

admin.py

```python
from django.contrib import admin
admin.site.register(ModelName)
```

### Adminでのモデルの表現方法を扱う

admin.py

```python
from django.contrib import admin

class ModelNameAdmin(admin.ModelAdmin):
  # something
admin.site.register(ModelName, ModelNameAdmin)
```

または

```python
from django.contrib import admin

@admin.register(ModelName)
class ModelNameAdmin(admin.ModelAdmin):
  # something
```

### Adminで表示するフィールドを変更する

```python
from django.contrib import admin

@admin.register(ModelName)
class ModelNameAdmin(admin.ModelAdmin):
  fields = ('name', 'title', 'date')
```

これを設定しない場合は、ModelName.\_\_str\_\_ が使われる。
