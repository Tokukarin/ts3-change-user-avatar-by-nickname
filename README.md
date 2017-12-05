# ts3-change-user-avatar-by-nickname

BACKUP DATABASE AND TEAMSPEAK3 FOLDER BEFORE USING !!!! 

First working version, tested only on 3.0.13.6 Teamspeak Server. 

<b><a href="https://github.com/cryptozealot/ts3-change-user-avatar-by-nickname/blob/master/ts3chavatar.sh">ts3chavatar.sh</a> allows the owner of ts3 server on a linux machine to change an user's avatar with given: username, picture and path to teamspeak directory. It does that by overwriting the old avatar file with the new one and editing the database to set new avatar hash.</b>

\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/

<b>Prerequisites:</b>
<i>sqlite3</i>
Install "sqlite3" with your packet manager:
<blockquote>apt-get install sqlite3</blockquote>
<blockquote>yum install sqlite3</blockquote>

<b>Parameters</b>

<ul><li>Nickname of user</li><li>Full path of picture</li><li>Full path where ts3 is installed</li></ul>

<b>Usage</b>

<blockquote><B>./ts3chavatar.sh {NICKNAME} {FULL_PATH_OF_PIC} {FULL_PATH_OF_TS3} </B></blockquote>

<b>Example:</b>

<blockquote>

./ts3chavatar.sh ts3user /home/ubuntu/picture123.jpg /home/teamspeak/

</blockquote>


NOTES : 


TO DO: Get ts3 path automatically, multiple servers in one db ??

SQL Querries for testing:

<blockquote>
get UID

SELECT client_unique_id from clients where client_nickname='tester1';

get ID

SELECT client_id from clients where client_nickname='tester1';

set avatar md5hash

UPDATE client_properties SET value='b3b3b8e6d973385716fb320b77331f78' WHERE ident='client_flag_avatar' AND id='3689';

get md5 to input in table 

md5sum {filename}
</blockquote>
