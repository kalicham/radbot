import telebot
from telebot import types

bot = telebot.TeleBot('1237837770:AAEvJeRdlGxwjaW0HpYl-rEjUQJPdGkpitU')


#@bot.message_handler(commands=['start'])
#def start_message(message):
#    bot.send_message(message.chat.id, 'Привет, ты попал к чат-боту RADFLIP.'
#                                      'Выбери, что тебе нравиться?')

@bot.message_handler(commands=["start"])
def start(m):
    msg = bot.send_message(m.chat.id, 'Привет, ты попал к чат-боту RADFLIP. '
                                      'Скажи, что тебе нравиться?')
    keyboard = types.ReplyKeyboardMarkup(resize_keyboard=True)
    keyboard.add(*[types.KeyboardButton(name) for name in ['Хочу учиться!']])
    keyboard.add(*[types.KeyboardButton(name) for name in ['Хочу работать!']])
    bot.send_message(m.chat.id, 'Выбирай смелее!',
        reply_markup=keyboard)
    bot.register_next_step_handler(msg, name)

def name(m):
    if m.text == 'Хочу работать!':
        keyboard = types.ReplyKeyboardMarkup(resize_keyboard=True)
        keyboard.add(*[types.KeyboardButton(advert) for advert in ['Назад']])
        bot.send_message(m.chat.id, 'Переходи к нам на RADHUB.'
                                    'Переходи на сайт - Выполняй задания - Жди ответа',
            reply_markup=keyboard)
    elif m.text == 'Хочу учиться!':
        keyboard = types.ReplyKeyboardMarkup(resize_keyboard=True)
        keyboard.add(*[types.KeyboardButton(advert) for advert in ['Назад']])
        bot.send_message(m.chat.id, 'Сожалею, Коля еще готовит курс(',
            reply_markup=keyboard)

bot.polling()
