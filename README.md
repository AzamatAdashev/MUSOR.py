import discord
from discord.ext import commands
intents = discord.Intents.default()
intents.message_content = True

bot = commands.Bot(command_prefix='$', intents=intents)
@bot.event
async def on_ready():
    print(f'We have logged in as {bot.user}')
@bot.command()
async def sorting(ctx):
    await ctx.send(f'Есть несколько видов мусора: пластик, стекло, бумага, несортируемые отходы. Каждый вид надо класть в отдельный контейнер.')
@bot.command()
async def dirty(ctx):    
    await ctx.send(f'Если не сортировать мусор, природа будет загрязняться и мы все умрем.')
bot.run()
