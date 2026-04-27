import os
import telebot
from telebot import types

TOKEN = os.getenv("BOT_TOKEN")
bot = telebot.TeleBot(TOKEN)

@bot.message_handler(commands=['start'])
def start(message):
    markup = types.ReplyKeyboardMarkup(resize_keyboard=True)
    markup.row("🎮 Играть", "🏆 Рейтинг")
    markup.row("💎 VIP", "🎁 Бонус")
    markup.row("👥 Позвать друга")

    bot.send_message(
        message.chat.id,
        "🔥 Добро пожаловать в Рискни или Слейся!\n\nЗдесь слабые сливаются.",
        reply_markup=markup
    )

@bot.message_handler(func=lambda m: True)
def menu(message):
    text = message.text

    if text == "🎮 Играть":
        markup = types.ReplyKeyboardMarkup(resize_keyboard=True)
        markup.row("🔥 Рискну", "💤 Сольюсь")
        markup.row("🏠 Меню")

        bot.send_message(
            message.chat.id,
            "Тебе предлагают 1000€ за ночную поездку с незнакомцем.\nЧто выберешь?",
            reply_markup=markup
        )

    elif text == "🔥 Рискну":
        bot.send_message(message.chat.id, "🔥 Ты рискнул.\n+150 очков")

    elif text == "💤 Сольюсь":
        bot.send_message(message.chat.id, "💤 Ты слился.\nИногда это умный ход.")

    elif text == "🏆 Рейтинг":
        bot.send_message(message.chat.id, "🏆 Топ игроков:\n1. Max — 3200\n2. Alex — 3000")

    elif text == "💎 VIP":
        bot.send_message(message.chat.id, "💎 VIP режим скоро будет доступен.")

    elif text == "🎁 Бонус":
        bot.send_message(message.chat.id, "🎁 Бонус дня: +50 очков")

    elif text == "👥 Позвать друга":
        bot.send_message(message.chat.id, "👥 Пригласи друзей в игру!")

    elif text == "🏠 Меню":
        start(message)

bot.infinity_polling()
