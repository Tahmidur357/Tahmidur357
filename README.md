- 👋 Hi, I’m @Tahmidur357
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Tahmidur357/Tahmidur357 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
from telegram import Update
from telegram.ext import ApplicationBuilder, CommandHandler, MessageHandler, Filters, ContextTypes

async def start(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text("স্বাগতম! আমি আপনার সহায়ক বট। আপনার কাজ কীভাবে করতে পারি?")

async def help_command(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text("কমান্ডসমূহ:\n/start - শুরু করুন\n/help - সাহায্য নিন\n/about - বট সম্পর্কে জানুন")

async def about(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text("আমি একটি টেলিগ্রাম বট যা আপনাকে বিভিন্ন তথ্য এবং মজাদার সেবা প্রদান করতে পারি!")

async def handle_message(update: Update, context: ContextTypes.DEFAULT_TYPE):
    text = update.message.text.lower()
    if "hello" in text:
        await update.message.reply_text("হ্যালো! কেমন আছেন?")
    elif "bye" in text:
        await update.message.reply_text("বিদায়! আবার দেখা হবে!")
    else:
        await update.message.reply_text("আপনার কথাটি বুঝতে পারলাম না।")

if __name__ == '__main__':
    app = ApplicationBuilder().token("YOUR_BOT_TOKEN").build()

    app.add_handler(CommandHandler("start", start))
    app.add_handler(CommandHandler("help", help_command))
    app.add_handler(CommandHandler("about", about))
    app.add_handler(MessageHandler(Filters.text & ~Filters.command, handle_message))

    print("Bot is running...")
    app.run_polling()app.add_handler(CommandHandler("start", start))
app.add_handler(CommandHandler("help", help_command))
app.add_handler(CommandHandler("about", about))
app.add_handler(MessageHandler(Filters.text & ~Filters.command, handle_message))

print("Bot is running...")
app.run_polling()
    
