<!--
 * @Author: HK560
 * @Date: 2021-12-31 16:00:49
 * @LastEditTime: 2022-01-03 17:25:57
 * @LastEditors: HK560
 * @Description:
 * @FilePath: \NorthStarCN_WIKI\Doc\cliForServer.md
-->
# 服務端命令
以下皆为示例
- +setplaylistvaroverrides "max_players 32" -maxplayersplaylist
- setplaylistvaroverrides "max_players 28 timelimit 20 scorelimit 750"
- SetPlaylistVarOverride( "custom_air_accel_pilot", "9000" ) 空速 写在.nut
- +sv_airaccelerate 5000
- +setplaylist private_match +setplaylist ps 
- +mp_gamemode ps 
- +map mp_lf_stacks 
- +setplaylistvaroverrides "scorelimit 750" 
- +setplaylistvaroverrides "timelimit 20" 
- +setplaylistvaroverrides "max_players 28" -maxplayersplaylist 
# gift
Gift Mod
--
Basically most of it was inspired by Icepick's method of spawning in weapons, but now you'll be able to gift everyone or certain players on your server certain weapons/tacticals/abilites.

There are two commands in this mod:

gift  weaponId playerId mods1 mods2 mods3

mod mod1 mod2 mod3

Typing gift by itself will print out every player's name + their playerId.

You can lookup weaponIds by typing give and pressing Tab to cycle through the multiple weapon IDS.

Typing mod by itself will print out every single weapon mods available. Do keep in mind that some weapon mods conflict with certain weapons and will result in a crash. (Ex. CARs can't have variable scope or ricochet mods. Every weapon also cannot have more than 4 mods.)

Some examples:

gift mp_weapon_sniper all will remove their primary weapon and replace it with a Kraber.

gift mp_titanweapon_leadwall 2 will remove the player with an ID of 2's primary weapon and replace it with a Leadwall.

gift mp_titanweapon_sniper all 1 5 6 will give everyone a instant charging, amped, fast reloading plasma railgun.

gift mp_weapon_smart_pistol 12 take a guess.
mod 1 will add/remove the second mod available on your weapon.

Notes:
- Weapons don't persist after death.
- Beware that some weapon IDs are developer weapons and could result in a crash if misused.
- Cores are only available for Titans, the icon at the bottom left won't change but the core would function. Sword Core requires Ronin's sword


# ADMIN ABUSE MOD
--
Want to bully anyone who joins your server? Look no further with this mod! Now you can
- slay someone/imc/militia/all
- switchteam/st someone/imc/militia/all
- respawn/rpwn someone/imc/militia/all
- gift command from Gift Mod gift <weaponId> <someone/imc/militia/all> <mods1> <mods2> <mods3>
- rearm someone/imc/militia/all to refill tacticals/abilities/cores
- fly someone/imc/militia/all to noclip
- titanfall/tf <someone/imc/militia/all>
-  teleport <someone/imc/militia/all> <someone/crosshair> teleport everybody to your crosshair, teleport someone to another person, teleport everyone to you,
    teleport one team to your crosshair
- remove someone/team/all main weapons
- freeze someone/team/all
- unfreeze someone/team/all
- hp/health someone/team/all to change max hp, 100 for base pilot, 2500 per bar for titans
- announce someone/team/all <word1> <word2> <word3>
- getteam someone
- 'shuffleteam/shuffleteams check AutoBalance instead for better one
- v/vanish someone/IMC/militia/all
- uv/unvanish someone/IMC/militia/all

so, yeah. enjoy your players malding probably


### config
- net_chan_limit_mode 2 // kick clients that go over the limit
- net_chan_limit_msec_per_sec 100 // number of milliseconds of server netchan processing time clients can use per second before getting kicked
- sv_querylimit_per_sec 10 // number of connectionless packets clients can send to this server per second without getting blocked
- base_tickinterval_mp 0.016666667 // default tickrate: 60 tick
- sv_updaterate_mp 60 // default updaterate: 20 tick
- sv_minupdaterate 60 // unsure if this actually works, but if it does, should set minimum client updaterate
- sv_max_snapshots_multiplayer 1200 // this needs to be updaterate * 15, or clients will dc in killreplay
- net_data_block_enabled 0 // not really sure on this, have heard datablock could have security issues? doesn't seem to have any adverse effects being disabled
- host_skip_client_dll_crc  1 // allow people to run modded client dlls, this is mainly so people running pilot visor colour mods can keep those, since they use a client.dll edit
- net_maxfilesize 64
- net_maxroutable 2400
- net_maxfragments 2400
- sv_usercmd_max_queued 80
- sv_maxvelocity 150000