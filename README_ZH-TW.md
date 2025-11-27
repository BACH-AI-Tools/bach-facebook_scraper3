# Facebook Scraper3 MCP Server

[English](./README_EN.md) | [简体中文](./README.md) | 繁體中文

## 🚀 使用 EMCP 平台快速體驗

**[EMCP](https://sit-emcp.kaleido.guru)** 是一個強大的 MCP 伺服器管理平台，讓您無需手動配置即可快速使用各種 MCP 伺服器！

### 快速開始：

1. 🌐 造訪 **[EMCP 平台](https://sit-emcp.kaleido.guru)**
2. 📝 註冊並登入帳號
3. 🎯 進入 **MCP 廣場**，瀏覽所有可用的 MCP 伺服器
4. 🔍 搜尋或找到本伺服器（`bach-facebook_scraper3`）
5. 🎉 點擊 **「安裝 MCP」** 按鈕
6. ✅ 完成！即可在您的應用中使用

### EMCP 平台優勢：

- ✨ **零配置**：無需手動編輯配置檔案
- 🎨 **視覺化管理**：圖形介面輕鬆管理所有 MCP 伺服器
- 🔐 **安全可靠**：統一管理 API 金鑰和認證資訊
- 🚀 **一鍵安裝**：MCP 廣場提供豐富的伺服器選擇
- 📊 **使用統計**：即時查看服務調用情況

立即造訪 **[EMCP 平台](https://sit-emcp.kaleido.guru)** 開始您的 MCP 之旅！


---

## 簡介

這是一個 MCP 伺服器，用於存取 Facebook Scraper3 API。

- **PyPI 套件名**: `bach-facebook_scraper3`
- **版本**: 2.0.0
- **傳輸協定**: stdio


## 安装

### 从 PyPI 安装:

```bash
pip install bach-facebook_scraper3
```

### 从源码安装:

```bash
pip install -e .
```

## 运行

### 方式 1: 使用 uvx（推荐，无需安装）

```bash
# 运行（uvx 会自动安装并运行）
uvx --from bach-facebook_scraper3 bach_facebook_scraper3

# 或指定版本
uvx --from bach-facebook_scraper3@latest bach_facebook_scraper3
```

### 方式 2: 直接运行（开发模式）

```bash
python server.py
```

### 方式 3: 安装后作为命令运行

```bash
# 安装
pip install bach-facebook_scraper3

# 运行（命令名使用下划线）
bach_facebook_scraper3
```

## 配置

### API 認證

此 API 需要認證。請設定環境變數:

```bash
export API_KEY="your_api_key_here"
```

### 環境變數

| 變數名 | 說明 | 必需 |
|--------|------|------|
| `API_KEY` | API 金鑰 | 是 |
| `PORT` | 不適用 | 否 |
| `HOST` | 不適用 | 否 |



### 在 Claude Desktop 中使用

编辑 Claude Desktop 配置文件 `claude_desktop_config.json`:


```json
{
  "mcpServers": {
    "facebook_scraper3": {
      "command": "uvx",
      "args": ["--from", "bach-facebook_scraper3", "bach_facebook_scraper3"],
      "env": {
        "API_KEY": "your_api_key_here"
      }
    }
  }
}
```

**注意**: 請將 `E:\path\to\facebook_scraper3\server.py` 替換為實際的伺服器檔案路徑。


## 可用工具

此服务器提供以下工具:


### `comment_by_id`

Get comment by comment id

**端点**: `GET /comment`


**参数**:

- `comment_id` (string) *必需*: Example value: 2815848835278004



---


### `search_people`

Searches people

**端点**: `GET /search/people`


**参数**:

- `query` (string) *必需*: Example value: pizza

- `cursor` (string): Example value: 



---


### `search_hashtag`

Search posts with hashtag

**端点**: `GET /search/hashtags`


**参数**:

- `hashtag` (string) *必需*: Example value: gol

- `cursor` (string): Example value: 



---


### `profile_reels`

Get profile reels. Get `reels_profile_id` from profile details endpoint

**端点**: `GET /profile/reels`


**参数**:

- `reels_profile_id` (string) *必需*: Example value: YXBwX2NvbGxlY3Rpb246cGZiaWQwUHNSMVVqTTE3a2dicGQ1VVkycEhwcGtKV2dwOFltNHpxUU53U3JCRTluUUZmQ3o0dG9tMjNLaWlTVnNzZmpNQnlDWVoxQWtjTXNlVmlveWdFeGw=

- `cursor` (string): Example value: 



---


### `page_events`

Get all future events created by page

**端点**: `GET /page/events/future`


**参数**:

- `page_id` (string) *必需*: Example value: 100063667778486

- `cursor` (string): Example value: 

- `collection_id` (string): Example value: 



---


### `post_reactions`

Get post reactions

**端点**: `GET /post/reactions`


**参数**:

- `post_id` (string) *必需*: Example value: 2253766361810327

- `cursor` (string): Example value: 



---


### `comments___nested`

Get nested comments. You need to use legacy fb id

**端点**: `GET /post/comments_nested`


**参数**:

- `post_id` (string): Example value: 979891387516215

- `comment_id` (string): legacy_comment_id

- `expansion_token` (string): Example value: MjoxNzM3OTY2Mzk0OgF1awP-xdBTo30UnnZUyhtyeebg0jVPoVV4mPROM1cOYWTDR5SCnvo6iBi20bz8LOYiG8vLdH6MB7q-43BaIT4TuTSDOaTc6RuXysoOhSqAVJA0_WcLrgUn8XQK-RiWnu1_pzCvCo8quhTgHDUvkAVRvV-Cun1kyY3xbgsW_43rvGoObIdFqDsduFTaPu2H440xn6U9b0uKIG7HEVDuTPkjF-KUBds0l_m3DiKRhCA4frRbr1vbRG6f2Mbf4nw4yhKhjIHFe9CTXpYlvZAVf6LqF84O2167FRMyOWSR1x1YIBURLRSRL_azSdTcpPHVV3E_fUzb3nXT3aq7I3TLeHqPJp2kAU-bCas-Tq_BjcK1mQbFUPBR9R0LpNGaNRMMdFwkCouRuvktHEZa1-6maYUw



---


### `page_reels`

Get page reels by page id - use reels_page_id now

**端点**: `GET /page/reels`


**参数**:

- `page_id` (string): legacy - migrate to reels_page_id

- `cursor` (string): Example value: 

- `reels_page_id` (string): Value used by facebook. Get it from page details endpoint



---


### `listing_details`

Get listing details

**端点**: `GET /marketplace/details`


**参数**:

- `listing_id` (string) *必需*: Example value: 750003161080442



---


### `search`

Search marketplace. Use cursor to get next page

**端点**: `GET /marketplace/search`


**参数**:

- `query` (string) *必需*: Example value: pizza

- `lat` (string) *必需*: Example value: 40.7128

- `lng` (string) *必需*: Example value: -74.006

- `price_min` (string): Example value: 

- `price_max` (string): Example value: 

- `radius_km` (string): Example value: 

- `condition` (string): used_like_new , used_good, used_fair , new Can be combined with coma, for example: used_like_new,used_good

- `category` (string): cars, boats etc.



---


### `comments`

Get post comments. Use comment_id from post

**端点**: `GET /post/comments`


**参数**:

- `post_id` (string) *必需*: Example value: pfbid02BzYRNmoznsZjci5FuztPUb9mKd9ameNVYSBweaBEvb8oEzSMjcs8nbXnMkYA5Benl

- `cursor` (string): Example value: 



---


### `search_groups_posts`

Searches group for posts

**端点**: `GET /search/groups_posts`


**参数**:

- `query` (string) *必需*: Example value: Be my friend

- `cursor` (string): Example value: 

- `group_id` (string): Example value: 137206643664121

- `start_date` (string): Example value: 

- `end_date` (string): Example value: 



---


### `page_videos`

Get page videos by page delegate id.  YOU NEED TO USE DELEGATE ID, NOT PAGE ID.

**端点**: `GET /page/videos`


**参数**:

- `delegate_page_id` (string) *必需*: Example value: 20531316728

- `cursor` (string): Example value: 



---


### `pages_photos`

Read page photos (from recent)  Use cursor to get next page of results

**端点**: `GET /page/photos`


**参数**:

- `page_id` (string) *必需*: Example value: 100064830872783

- `cursor` (string): Example value: 

- `collection_id` (string): Required with cursor. Obtain from first response



---


### `pages_posts`

Read page posts (from recent)

**端点**: `GET /page/posts`


**参数**:

- `page_id` (string) *必需*: Example value: 100064860875397

- `cursor` (string): Example value: 

- `start_date` (string): Example value: 

- `end_date` (string): Example value: 



---


### `page_details`

Read page details

**端点**: `GET /page/details`


**参数**:

- `url` (string) *必需*: Example value: https://www.facebook.com/facebook



---


### `page_past_events`

Get all past events created by page. Use cursor to get next page of results.

**端点**: `GET /page/events/past`


**参数**:

- `page_id` (string) *必需*: Example value: 100063667778486

- `cursor` (string): Example value: 

- `collection_id` (string): Example value: 



---


### `get_group_posts`

Get group posts.  Only PUBLIC groups can be scrapped! If there are no post response, check if group is not private.

**端点**: `GET /group/posts`


**参数**:

- `group_id` (string) *必需*: Example value: 1439220986320043

- `cursor` (string): Example value: 

- `sorting_order` (string): Example value: 



---


### `get_group_future_events`

Get group future events.  Only PUBLIC groups can be scrapped! If there are no post response, check if group is not private. Use cursor to get next page of events!

**端点**: `GET /group/future_events`


**参数**:

- `group_id` (string) *必需*: Example value: 1571965316444595

- `cursor` (string): Example value: 



---


### `search_events`

Searches for facebook events

**端点**: `GET /search/events`


**参数**:

- `query` (string) *必需*: Example value: beer

- `cursor` (string): Example value: 

- `location_uid` (string): Example value: 

- `start_date` (string): Example value: 

- `end_date` (string): Example value: 



---


### `game_lives`

Get game live videos Use cursor to get next page.

**端点**: `GET /gaming/live`


**参数**:

- `game_id` (string) *必需*: Example value: 1494097103958822

- `cursor` (string): Example value: 

- `sort_order` (string) *必需*: Example value: 



---


### `browse_games`

Browse games.  Use empty query for browse all games. Use cursor to get next page.

**端点**: `GET /gaming/games`


**参数**:

- `query` (string) *必需*: Example value:  

- `cursor` (string): Example value: 

- `sort_order` (string) *必需*: Example value: 



---


### `page_reviews`

Get page reviews. Use cursor to get next page

**端点**: `GET /page/reviews`


**参数**:

- `page_id` (string) *必需*: Example value: 100063543614476

- `cursor` (string): Example value: 



---


### `search_video`

Performs facebook videos search

**端点**: `GET /search/videos`


**参数**:

- `query` (string) *必需*: Example value: facebook

- `cursor` (string): Example value: 

- `recent_videos` (string): Example value: 

- `location_uid` (string): Example value: 

- `start_date` (string): Example value: 

- `end_date` (string): Example value: 



---


### `profile_posts`

Read profile posts (from recent), if public

**端点**: `GET /profile/posts`


**参数**:

- `profile_id` (string) *必需*: Example value: 4

- `cursor` (string): Example value: 

- `start_date` (string): Example value: 

- `end_date` (string): Example value: 



---


### `events_details_by_id`

Get events details by event id

**端点**: `GET /event/details_id`


**参数**:

- `event_id` (string) *必需*: Example value: 1259800548576578



---


### `locations`

Search for facebook locations id. If you get strange results, try add country to query and/or try without diacritic

**端点**: `GET /search/locations`


**参数**:

- `query` (string) *必需*: Example value: 



---


### `search_post`

Performs facebook posts search

**端点**: `GET /search/posts`


**参数**:

- `query` (string) *必需*: Example value: facebook

- `cursor` (string): Example value: 

- `recent_posts` (string): Example value: 

- `location_uid` (string): Example value: 

- `start_date` (string): Example value: 

- `end_date` (string): Example value: 



---


### `events_details_by_url`

Get events details

**端点**: `GET /event/details`


**参数**:

- `url` (string) *必需*: Example value: https://www.facebook.com/events/456725590572335



---


### `profiles_details_by_id`

Get profiles details by id

**端点**: `GET /profile/details_id`


**参数**:

- `profile_id` (string) *必需*: Example value: 



---


### `profile_details_by_url`

Get profile details by url

**端点**: `GET /profile/details_url`


**参数**:

- `url` (string) *必需*: Example value: 



---


### `profile_id`

Get profile id by url

**端点**: `GET /profile/profile_id`


**参数**:

- `url` (string) *必需*: Example value: 



---


### `get_post_details`

Get post details by url or post id. If both are set, post id is used.

**端点**: `GET /post`


**参数**:

- `post_id` (string): Example value: pfbid04KTWEM9Rri6Wg3oLRBF5FUUvfPebQ6ZJRwVivymc8e8KWvy3RsnpUXyppjEZqkwZl

- `post_url` (string): Example value: 



---


### `get_group_details`

Get group summary

**端点**: `GET /group/details`


**参数**:

- `url` (string) *必需*: Example value: https://www.facebook.com/groups/gieldagryplanszowe



---


### `get_group_id`

Getting group facebook id

**端点**: `GET /group/id`


**参数**:

- `url` (string) *必需*: Example value: https://www.facebook.com/groups/gieldagryplanszowe



---


### `page_id`

get page id from url

**端点**: `GET /page/page_id`


**参数**:

- `url` (string) *必需*: Example value: https://facebook.com/facebook



---


### `reshares`

Get post reshares

**端点**: `GET /post/share`


**参数**:

- `post_id` (string): use share_id from post details

- `cursor` (string): Example value: 



---


### `search_place`

Search for fb place

**端点**: `GET /search/places`


**参数**:

- `query` (string) *必需*: Example value: pizza

- `cursor` (string): Example value: 

- `location_uid` (string): Example value: 



---


### `search_pages`

Searches for facebook pages

**端点**: `GET /search/pages`


**参数**:

- `query` (string) *必需*: Example value: beer

- `cursor` (string): Example value: 

- `location_uid` (string): Example value: 



---



## 技术栈

- **传输协议**: stdio
- **HTTP 客户端**: httpx

## 开发

此伺服器由 [API-to-MCP](https://github.com/BACH-AI-Tools/api-to-mcp) 工具自動生成。

版本: 2.0.0
