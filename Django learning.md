* static配置问题 `如何使css等样式文件生效`

  在STATIC_URL语句之外再添加一个语句STATICFILES_DIRS，用于放置自定义的样式文件地址
  ```
  # Static files (CSS, JavaScript, Images)
  # https://docs.djangoproject.com/en/1.11/howto/static-files/

  STATIC_URL = '/static/'

  STATICFILES_DIRS = [
      os.path.join(BASE_DIR, "static/"),
  ]
  ```
