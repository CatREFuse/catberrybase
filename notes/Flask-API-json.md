---
title: Daily-2022-01-17 星期一
Date: 2022-01-17
type: fe
tags: flask, python
---

# Flask 接口返回乱码

本质上是没有设置返回 Header 中的 `Content-Type` 字段，需要设置成 `application/json;charset=UTF-8`

```python
@app.route('/assets/<file_name>', methods=['GET'])
def get_assets(file_name: str = 'engines.json'):
    print('get assets')
    return send_from_directory('./assets', file_name), 200, [('Content-Type', 'application/json;charset=UTF-8')]
```
