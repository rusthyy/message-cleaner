token = "YOU_TOKEN"
prefix = "" 

#--- BOT ---

import discord
from discord.ext import commands

bot = commands.Bot(command_prefix=prefix, self_bot=True)
bot.remove_command("help")

@bot.event
async def on_ready():
    print("\n\n[Prefix] clear") 
    print(f"[Welcome] {bot.user.name}")
    print(f"[Welcome] {bot.user.id}\n\n")

@bot.command()
async def clear(ctx, limit: int=None):
    passed = 0
    failed = 0
    async for msg in ctx.message.channel.history(limit=limit):
        if msg.author.id == bot.user.id:
            try:
                await msg.delete()
                passed += 1
            except:
                failed += 1
    print(f"[Complete] Removed {passed} messages with {failed} fails")

bot.run(token, bot=False)
