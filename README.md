# hellniggafrom aiogram import Bot, types
from aiogram.dispatcher import Dispatcher
from aiogram.utils import executor
from aiogram import ReplyKeyboardRemove, \
    ReplyKeyboardMarkup, ReplyKeyboard, \
    InlineKeyboardMarkup, InlineKeyboardButton


TOKEN = '6348129789:AAGYqJUYjUNMokEEutj-wugepJ61j7v6sfw'
bot = Bot(token=TOKEN)
dp = Dispatcher(bot)

button_hi = KeyboardButton('кевк')
button_next = KeyboardButton('Подробнее')
next_text = ReplyKeyboardMarkup(resize_keyboard=True).add(button_next)
greet_kb1 = ReplyKeyboardMarkup(resize_keyboard=True).add(button_hi)
button2 = KeyboardButton('кувк')
button3 = KeyboardButton('кивк')
markup = ReplyKeyboardMarkup(resize_keyboard=True).row(button2, button3)



@dp.message_handler(commands=['start'])
async def process_start_command(message: types.Messge):
    await message.reply('Здарова!\nНапиши мне!', reply_markup=greet_kb1)
    from random import randint
    @dp.message_handler()
    asunc def dialog(message: types.Message):
    if message.text == "HI":
        await message.answer('Hi my student')
    elif message.text == 'кювк':
        await.message.answer('ok',reply_markup=greet_kb1)
    elif message.text == 'кявк':
        await message.answer('Ok',reply_markup=markup)
    elif message.text == 'кывк':
        number = randint(1,3)
        if number == 1:
            photo = open('Photo\one.png', 'rb')
        elif number == 2:
            photo = open ('photo.png', 'rb')
        else:
            photo = open('photo.png', 'rb')
            await bot.send_photo(message.chat.id.photo)
            await message.answer('DUHI')
        elif message.text == 'кэвк':
            video = open('video')
            await bot.send_video(message.chat.id, video)
            await message.answer('Ok')
        elif message.text == 'кёвк':
            audio = open('audio')
            await bot.send_audio(message.chat.id, audio)

        else:
            await message.answer('I don`t understand you')
        if__name__ == '__name__':
        executor.start_polling(dp)
