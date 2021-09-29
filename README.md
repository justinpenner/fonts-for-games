![alt text](https://github.com/justinpenner/fonts-for-games/blob/main/cover.png?raw=true)

# Fonts for video games: overlooked and underserved

This repo contains the script from my 2021 presentation at TypeWknd (linked below), and a PDF of the slide deck.

https://2021.typewknd.com/conference/fonts-for-video-games-overlooked-and-underserved

## Introduction

Alright, hey everyone! I'm [Justin Penner](https://justinpenner.ca/), and I'm a typeface designer based in Vancouver, Canada. This presentation is about fonts and video game development. I've been researching how game developers use fonts, and I've made a lot of interesting discoveries, which I'll break up into 3 parts in this talk:

In the first part, I'm going to talk about how game developers use fonts, how fonts work in game engines, and some of the technical considerations that type designers may want to take into account when designing fonts for games.

In the second part, I want to look at what sorts of opportunities there might be for type designers and foundries to work on fonts specifically for game developers to use.

And in the third part, I'll focus on how type designers and foundries can help build a better ecosystem for fonts and typography in video games.

## Section 01: Font support in game engines

Game developers can use a wide array of software engines to develop games, and each engine has different capabilities for importing fonts and rendering them in-game.

First, for some background, [Unity](https://unity.com/) and [Unreal](https://www.unrealengine.com/) are the two game engines you'll hear about most. They're by far the most popular game engines, and are used for a lot of top tier blockbuster games. Then of course, there are many smaller game engines like [Godot](https://godotengine.org/) or [RPG Maker](https://www.rpgmakerweb.com/), which are popular among indie game creators.

In most game engines, you import assets into your project before you can use them. Assets can be images, sprites, 3D models, audio clips, or in this case—fonts.

Most of us are probably familiar with how to install a font and use it in a graphic design or desktop publishing app, or maybe how to embed a font in a website, but importing fonts into a game engine is a very different process.

Most game engines require fonts to be rasterized first, before they can be used in the game project. In a 2-dimensional game, sprite sheets are commonly used to combine many images into one file, or technically two files – the second file contains coordinates that map out the positions of the images. Fonts in games work the same way, and one format you'll often encounter is called BMFont, which is usually a PNG image accompanied by a text file, or an XML or JSON file that contains the coordinates of all the glyphs and their Unicode codepoints, as well as kerning which is supported in this format.

In 3D game engines, you still don't get to use fonts in any kind of vector format. Modern gaming hardware is heavily optimized for rendering 3D mesh objects and then applying textures to them. So, fonts and other image assets still need to be rasterized in most cases, since the text that you might see in-game would be applied as a texture onto a 3D model. So, importing fonts into a 3D game still means you'll be rasterizing the font onto a sprite sheet, or in some game engines you might use a type of raster image called a signed distance field, which I won't go into too much detail but it's sort of a vector/raster hybrid format, where the image is saved as a raster, but it's rendered mathematically as solid shapes with hard edges, which gives you much sharper text in 3D environments.

So, since most game engines require fonts to be rasterized before importing into a game project, that means there's very little support for any kind of OpenType features or text shaping. No ligatures, no contextual alternates, no shaping for complex scripts like Arabic and Devanagari.

## Section 02: Opportunities for type designers & foundries in the game industry

So, the next question I want to answer is, what kinds of opportunities are there for type designers and foundries, in the gaming industry?

Well, that's one of the main reasons I wanted to do this talk, because I see some gaps where game developers aren't being served by type foundries, and some problems that need solving.

### Selling via game developer marketplaces

If you log onto a marketplace for game developers like [Itch.io](https://itch.io/), [ArtStation](https://www.artstation.com/), or Unreal and Unity's official marketplaces, you might find a few fonts, but not a lot of options. Sure, game developers can get fonts from the distributors we know like MyFonts, Adobe Fonts, Google Fonts, but that brings me to the next opportunity: licensing.

### Making licenses workable for game development

Font licensing can get really messy with game development. Being an independent type designer who recently started selling my own commercial fonts, I've researched and read a lot of font licenses from many different foundries, and I think there are some fundamental flaws in the way we write license terms, and how a game developer might interpret those terms.

For example, is a game an app? Probably yes, but what if it's a web-based game? Can you buy a web license, or do you need a much more expensive app license? What about the part in many font licenses that says you can basically do whatever you want with the font once it's "converted to outlines" or "rasterized"? A game developer could argue that they only need a desktop license in that case, if the fonts are rasterized when you import them into the game engine. But what if the type foundry argues that importing the font into a game engine constitutes modifying the font or converting the font format, which is often prohibited outright? Then the game developer has no workable license option.

Bottom line, there are a ton of type foundries out there whose license terms are at best confusing and at worst completely unworkable for game developers.

### More pixel fonts!

Not all game use pixel fonts, but they're enormously popular in both 2D *and* 3D games. Not enough type foundries take pixel fonts seriously, and it's actually quite difficult for a game developer to find a pixel font that meets their requirements. There are endless pixel fonts availabe, but the problems with them are endless too: many are unauthorized knock-offs of someone else's work, or they have very limited character sets, or the license terms are unclear and the designer is unreachable, or the font is just poorly designed. It's not uncommon for game creators to end up creating their own font for a project.

There's really a huge gap for reputable type foundries and designers to create high-quality pixel fonts with extended language support, for both text and display. Designing a pixel font is often very quick, so it's surprising that there aren't more options already.

## Section 3: Better typography in games

So, what can type designers and foundries do to help improve typography in video games?

### Game font licenses

I think improving licensing is the first step. I've read stories from indie game creators who just couldn't wrap their head around how to license fonts for their game, or major game development teams who couldn't get the font licensing past their legal department. I've even read comments from quite a few game developers who decided that they didn't need anything beyond a desktop license because the font software itself wasn't being embedded in the game due to pre-rasterizing.

I don't know what the best approach will be, but if you want to reach game developers, you need to either add a new type of license specifically for games, or make your app license terms work for the realities of how game development works.

### Design fonts for game engines

The next thing we can do to improve typography in games is to think about game engines while designing type, or to design fonts specifically for game developers.

Many game engines can import any font you like, but as I explained earlier, you don't get much more than the glyphs and their codepoints. How would you design a font for game development, knowing that kerning may or may not work, ligatures and alternates won't work, and all your glyphs will be pre-rasterized at an unknown size that may or may not have hinting applied? You might also have some developers that use signed distance fields for font rendering, which gives sharper edges when rendering type in 3D space, but also has the side effects of rounding all sharp corners in the glyphs.

### Help develop tools

One more important thing that's needed is more software tools related to typography and game development. We have a lot of brilliant coders and developers in our community, and I can think of at least a few needs that aren't being met with the current tools available for both type designers and game developers.

One good example is the [BMFont format](https://www.angelcode.com/products/bmfont/doc/file_format.html) for bitmap fonts, which is used by many game engines, but is not supported by most font editors. It would be great to see maybe some plugins to allow type designers to export directly to the BMFont format, and maybe even look for ways to extend the format to support more features beyond just kerning. The BMFont format is used widely among game engines, so I think it would be worth working on tools related to it.

It might also be nice to see some kind of a universal cross-platform tool for generating bitmap fonts, with both a command line and graphical interface. As it stands there are a few separate tools out there, but the one most game developers use is the original [BMFont app by AngelCode](https://www.angelcode.com/products/bmfont/), who developed the BMFont format, but the app is closed-source and Windows-only.

Lastly, I know some coders in our community are interested in improving tools like shaping engines, which enable support for languages with complex writing systems like Devanagari and Arabic. I don't know of a single game engine that fully supports complex writing systems, and most have zero support at all. I'm sure there are communities of for example Arabic game developers who have figured out some workarounds to develop games in Arabic with particular game engines, but the biggest problem is localization – many games are developed in English first, and then translated or localized so they can be released in different regions around the world, so it's really unfair if some languages are left out simply because they happen to use a complex writing system.

## Conclusion

So, if you're a type designer who's interested in the world of game development, I think there are a lot of opportunities out there. It feels to me like a bit of an untapped market, and the gaming market is huge – in fact it's bigger than a lot of people realise. The total global revenue for video games is actually more than films and music combined. I know most type foundries might not want to focus on one single vertical, but if you want to test the waters, I think the first thing to focus on is licensing. I think that's the biggest obstacle, so if you can find a solution for that, I think you'll be able to sell to game developers a lot more easily.

## Player Sans Mono

Finally, I want to wrap up with a giveaway for everyone. This is [Player Sans Mono](https://github.com/justinpenner/player-sans-mono), an 8x8 pixel font family in three weights plus an italic. The regular weight is loosely inspired by the famous Atari font that anyone who was a gamer in the 80s and 90s would have seen everywhere. You can find it in the TypeWknd Goodies Bag or on Github at the link below.

## Thanks

That's it! Thanks to everyone at TypeWknd, and here's a link to my slide deck if you're interested.
