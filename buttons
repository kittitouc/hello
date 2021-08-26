from discord.ext import commands
from discord_buttons_plugin import  *
import os
import discord
import re
from urllib import request
from urllib.parse import urlencode
import discord
from discord.ext.commands import context 
from discord.utils import get, oauth_url
from discord import FFmpegPCMAudio
from discordSuperUtils.Music import MusicManager
import youtube_dl
import asyncio
from async_timeout import timeout
from functools import partial
from discord.ext import commands, tasks
from datetime import datetime, timedelta
import itertools
from googletrans import Translator
import googletrans
from discord import channel, message
import random
import urllib
from discord.ext.tasks import loop
from discord.ext.commands import has_permissions, MissingPermissions
import itertools
import random
from discord.utils import get
import discord
from async_timeout import timeout
from discord.ext import commands
import os
from discord_components import (
    Button,
    ButtonStyle,
    Select,
    SelectOption,
)

bot = commands.Bot(command_prefix  =  ".")
buttons = ButtonsClient(bot)

@bot.event
async def on_ready():
    print(f'With ID: {bot.user.id}')
    print(f"Logged in as {bot.user.name}")
	
@bot.event
async def on_button_click(interaction):
    if interaction.component.label.startswith("Default Button"):
        await interaction.respond(type=5966, content='Button Clicked')

@bot.command()
async def c(ctx):
    await buttons.send(
	content = "This is an example message!", 
	channel = ctx.channel.id,
	components = [
		ActionRow([

			Button(label="Hello", style=ButtonStyle.blue, id="button_one"),

			Button(label = "it",style = ButtonStyle.red, id = "button_two"),

			Button(label = "me",style = ButtonStyle.green,id = "button_tree")
        ])
    ]
)


@buttons.click
async def button_one(ctx):
	embed = discord.Embed(title="คำสั่งlogout :sleeping:",description=(f'บายยยยยยยยยยยยยย!!'),color=0xFFC500)
	embed.set_footer(text="คำขอโดย: {}".format(ctx.member.display_name), icon_url=ctx.member.avatar_url)	
	await ctx.channel.send(embed=embed)
	await bot.logout()

@buttons.click
async def button_two(ctx):
	result = random.randint(1,6)
	embed = discord.Embed(colour = discord.Color.blue())

	embed.set_author(name='Rolling a dice! ⚀')
	await asyncio.sleep(0.1)
	msg = await ctx.channel.send(embed=embed)
        
	embed.set_author(name='Rolling a dice! ⚅')
	await asyncio.sleep(0.2)
	await msg.edit(embed=embed)

	embed.set_author(name='Rolling a dice! ⚂')
	await asyncio.sleep(0.3)
	await msg.edit(embed=embed)
        
	embed.set_author(name='Rolling a dice! ⚁')
	await asyncio.sleep(0.4)	
	await msg.edit(embed=embed)

	if result == 1:
		dicebox = "⚀"
	if result == 2:
		dicebox = "⚁"
	if result == 3:
		dicebox = "⚂"
	if result == 4:
		dicebox = "⚃"
	if result == 5:
		dicebox = "⚃"
	if result == 6:
		dicebox = "⚅"

	embed.set_author(name=f'Rolling a dice! {dicebox}')
	embed.add_field(name=f":game_die: The values are {result}",value='_ _',inline=False)
	embed.set_footer(text="คำขอโดย: {}".format(ctx.member.display_name), icon_url=ctx.member.avatar_url)
	await asyncio.sleep(0.1)
	await msg.edit(embed=embed)


@buttons.click
async def button_tree(ctx):
	embed = discord.Embed(description = f'me!',color=0xFFC500)
	embed.set_footer(text="คำขอโดย: {}".format((f'{ctx.member.display_name}')), icon_url=ctx.author.id)
	await ctx.send(embed=embed)


bot.run(os.getenv('TOKEN'))
