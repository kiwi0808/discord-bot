import discord
import sys
import time
import random
import asyncio
import time
import threading
import client
from discord import Client, client, message
from discord.ext import commands

token = "TOKEN HERE"

bot = commands.Bot(command_prefix='!')

@bot.event
async def on_member_join(member, message):
    member = discord.Member
    embed = discord.Embed(
        title=f"{member} joined!", description=f"{member} joined {member.guild}! We hope you enjoy {member.guild}!")
    await ctx.send(embed=embed)



@bot.command(name = 'question')
async def commands(message):
    await message.send('what is the 2 + 2?')
    time.sleep(3)
    if message.content == "4":
        await message.send("you are correct")
    else:
        await message.send( "you are a dummy" )




@bot.event
async def on_message(message):

    if message.content == "work":
        await message.channel.send( 'i hate work!' )
    elif message.content == "kiwi":
        await message.channel.send( 'i love kiwi' )
    elif message.content == "random":
        username1 = message.author.name
        if username1 == message.author.name:
            await message.channel.send( 'i love random crap' )
    elif message.content == "genius":
        await message.channel.send( 'you are a genius' )
    await bot.process_commands( message )


bot.run(token)  # recall my token was saved!
