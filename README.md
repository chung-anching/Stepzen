# Stepzen OpenAI
IBM Stepzen Demo OpenAI

## step.1 創建名為 OpenAI-0904 的資料夾 和api/OpenAI-0904的端點
stepzen init --endpoint=api/OpenAI-0904   
What would you like to call your workspace? 輸入 OpenAI-0904

## step.2 將建openai資料夾，並自動生成 index.graphql
stepzen import curl https://api.openai.com/v1/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer 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" \
  -d '{
	  "model": "text-davinci-003",
	  "prompt": "What is a language model and how is it related to AI?",
	  "temperature": 0.7,
	  "max_tokens": 256,
	  "top_p": 1,
	  "frequency_penalty": 0,
	  "presence_penalty": 0
	}' \
  --name openai \
  --query-name textCompletion \
  --query-type TextCompletion

  	CLI實作圖片示意如下：
  <img width="770" alt="截圖 2023-09-04 下午3 52 08" src="https://github.com/chung-anching/Stepzen/assets/59386373/ddfb5d24-51d8-4e52-8979-b6eea6f056e0">


## step.3 stepzen deploy
stepzen deploy

## step.4 開始輸入文字問題
stepzen request '{
  textCompletion(prompt: "What is a language model?") {
    choices { text }
  }
}'

## step.5 得到回應

# AI創造圖片
