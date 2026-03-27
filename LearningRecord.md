# Day 1

拆分奢侈品牌业务爬取流程，熟悉办公环境，安装编程软件

# Day 2

完成奢侈品牌业务设计，通过验收

![爬虫获取奢侈品牌信息](C:\Users\sys\Desktop\爬虫获取奢侈品牌信息.png)

设计爬取系统

![image-20260325095530343](C:\Users\sys\AppData\Roaming\Typora\typora-user-images\image-20260325095530343.png)

前端采用 Vue 3，后端采用FastAPI，uvicorn服务器

# Day 3

## 1优化爬虫程序

>*修复longcamp爬取bug,将原本通过script标签内JSON爬取逻辑改为从DOM标签中获取链接*

``` html
a.product-item__link[itemprop="url"]
```

>Balenciaga新增分页机制，抓取所有页的商品信息

``` python
if total_pages > 1:
                last_page_url = f"{self.official_url}?page={total_pages}"
                logger.info(f"[{self.brand_name}] 📡 请求最后一页: {last_page_url}")
                last_html = await self.fetch_page(last_page_url)
                last_soup = BeautifulSoup(last_html, 'html.parser')
                last_script = last_soup.find('script', {'id': '__NEXT_DATA__'})
                if last_script and last_script.string:
                    last_data = json.loads(last_script.string)
                    last_pld = last_data.get('props', {}).get('pageProps', {}).get('productListData', {})
                    products_data = last_pld.get('items', [])
                else:
                    products_data = product_list_data.get('items', [])
            else:
                products_data = product_list_data.get('items', []) or page_props.get('products', [])
```

>Dior修复原本串行逻辑，移除await关键字实现并行爬取

``` python
 semaphore = asyncio.Semaphore(self.CONCURRENCY)
	async def fetch_one(code: str) -> LuxuryProduct:
        async with semaphore:
            detail_url = self.DETAIL_API_TEMPLATE.format(code)
            detail_html = await self.fetch_page(detail_url)
            detail_data = json.loads(detail_html)
            return self._parse_product_detail(detail_data, code)
```

>DG
>
>需要携带cookie访问API获取商品数据，尝试使用drission模拟浏览器动态JS

## 2完成对产品用户评级的提示词

![CRM智能数据录入员任务分解](C:\Users\sys\Desktop\CRM智能数据录入员任务分解.png)

# D 4

完成爬虫项目优化，交付报告

# D 5

learning，详见gobig.md
