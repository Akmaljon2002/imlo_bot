from aiogram import Bot, Dispatcher, executor, types

Token = "5902882657:AAHP0HH94p4YJx_1dqx-MSgGIKHBrYkoowA"


bot = Bot(Token)
dp = Dispatcher(bot)

@dp.message_handler(commands='start')
async def salomlash(xabar:types.Message):
    await  xabar.answer(f"Assalomu alaykum ! {xabar.from_user.full_name} ! Bu yerdan bemani narsalarni yuklamang Do'stim😂")
    print(xabar.as_json())

@dp.message_handler()
async def wiki(xabar:types.Message):


	try:
		import requests

		url = "https://instagram-downloader-download-instagram-videos-stories.p.rapidapi.com/index"

		querystring = {"url": xabar.text}

		headers = {
			"X-RapidAPI-Key": "72b9faf34emsh28a8e006df1bd77p16a061jsn1852b726ce36",
			"X-RapidAPI-Host": "instagram-downloader-download-instagram-videos-stories.p.rapidapi.com"
		}

		response = requests.request("GET", url, headers=headers, params=querystring)

		video_link = response.json()['media']
		await xabar.answer_video(video_link)
	except:
		await xabar.answer("Noto'g'ri link")


if __name__ == '__main__':
    executor.start_polling(dp, skip_updates=True)
