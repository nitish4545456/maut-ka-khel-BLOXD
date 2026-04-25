const allowedPlayers = ["HASSANxSIGMA_","ShortStack_YT", "X_LITTLE_MONSTER_X"];
let commandsEnabled = true;

onPlayerChat = (playerId, chatMessage) => {
  if (!playerId) return false;
  
  if (chatMessage.substring(0, 1) !== "!") return;
  
  const name = api.getEntityName(playerId);
  if (!name) return false;
  
  const cmd = chatMessage.substring(1).trim().toLowerCase();
  
  if (!commandsEnabled && !allowedPlayers.includes(name) && cmd !== "allow") {
    api.sendMessage(playerId, "Commands are disabled.");
    return false;
  }
  
  if (cmd === "allow" && allowedPlayers.includes(name)) {
    commandsEnabled = true;
    api.broadcastMessage("Commands enabled.");
    return false;
  }
  
  if (cmd === "disallow" && allowedPlayers.includes(name)) {
    commandsEnabled = false;
    api.broadcastMessage("Commands disabled.");
    return false;
  }
  
  if (cmd === "clear") {
    api.clearInventory(playerId);
    api.sendMessage(playerId, "Inventory cleared.");
    return false;
  }
  
 // 🔥 SMP KIT (your FULL enchanted kit)
  if (cmd === "smp") {
    api.clearInventory(playerId);
    
    // Enchanted Weapons
    api.giveItem(playerId, "Diamond Sword", 1, {
      customAttributes: {enchantments: {"Damage": 3,"Attack Speed": 2}, enchantmentTier: "Tier 5"},
      customDisplayName: "Enchanted Sword",
      customDescription: ""
    });
    api.giveItem(playerId, "Diamond Pickaxe", 1, {
      customAttributes: {enchantments: {"Momentum": 2,"Break Speed": 3}, enchantmentTier: "Tier 5"},
      customDisplayName: "Enchanted Pickaxe",
      customDescription: ""
    });
    api.giveItem(playerId, "Diamond Bow", 1, {
      customAttributes: {enchantments: {"Attack Speed": 2,"Quick Charge": 3}, enchantmentTier: "Tier 5"},
      customDisplayName: "Enchanted Bow",
      customDescription: ""
    });
    api.giveItem(playerId, "Diamond Mace", 1, {
      customAttributes: {enchantments: {"Damage": 3,"Attack Speed": 2}, enchantmentTier: "Tier 5"},
      customDisplayName: "Enchanted Mace",
      customDescription: ""
    });
    api.giveItem(playerId, "Diamond Spear", 1, {
      customAttributes: {enchantments: {"Damage": 3,"Attack Speed": 2}, enchantmentTier: "Tier 5"},
      customDisplayName: "Enchanted Spear",
      customDescription: ""
    });
    
    // Enchanted Armor
    api.setItemSlot(playerId, 46, "Diamond Helmet", 1, {
      customAttributes: {enchantments: {Protection: 3, "Health Regen": 2}, enchantmentTier: "Tier 5"}
    });
    api.setItemSlot(playerId, 47, "Diamond Chestplate", 1, {
      customAttributes: {enchantments: {Protection: 3, "Health Regen": 2}, enchantmentTier: "Tier 5"}
    });
    api.setItemSlot(playerId, 48, "Diamond Gauntlets", 1, {
      customAttributes: {enchantments: {Protection: 3, "Health Regen": 2}, enchantmentTier: "Tier 5"}
    });
    api.setItemSlot(playerId, 49, "Diamond Leggings", 1, {
      customAttributes: {enchantments: {Protection: 3, "Health Regen": 2}, enchantmentTier: "Tier 5"}
    });
    api.setItemSlot(playerId, 50, "Diamond Boots", 1, {
      customAttributes: {enchantments: {Protection: 3, "Health Regen": 2}, enchantmentTier: "Tier 5"}
    });
    
    // SMP Items
    api.giveItem(playerId, "Diamond Hang Glider", 1);
    api.giveItem(playerId, "Iceball", 999);
    api.giveItem(playerId, "Baked Potato", 999);
    api.giveItem(playerId, "Net", 999);
    api.giveItem(playerId, "Diamond Spikes", 999);
    api.giveItem(playerId, "Mango", 999);
    api.giveItem(playerId, "Compressed Messy Stone", 999);
    api.giveItem(playerId, "Arrow of Poison", 999);
    api.giveItem(playerId, "Rainbow Firecracker", 999);
    api.giveItem(playerId, "Pear", 100);
    
    api.sendMessage(playerId, "🛠️ SMP KIT RECEIVED!", { color: "green" });
    return false;
  }
  
  // 🔥 UHC KIT (YOUR EXACT WORKING KIT)
  if (cmd === "uhc") {
    api.clearInventory(playerId);
    
    // YOUR EXACT UHC KIT ↓
    api.setItemSlot(playerId, 46, "Diamond Helmet", 1, {
      customAttributes: {
        enchantments: { Protection: 3, "Health Regen": 2, Damage: 10000000 },
        enchantmentTier: "Tier 5",
      },
    });
    api.setItemSlot(playerId, 47, "Diamond Chestplate", 1, {
      customAttributes: {
        enchantments: { Protection: 3, "Health Regen": 2 },
        enchantmentTier: "Tier 5",
      },
    });
    api.setItemSlot(playerId, 48, "Diamond Gauntlets", 1, {
      customAttributes: {
        enchantments: { Protection: 3, "Health Regen": 2 },
        enchantmentTier: "Tier 5",
      },
    });
    api.setItemSlot(playerId, 49, "Diamond Leggings", 1, {
      customAttributes: {
        enchantments: { Protection: 3, "Health Regen": 2 },
        enchantmentTier: "Tier 5",
      },
    });
    api.setItemSlot(playerId, 50, "Diamond Boots", 1, {
      customAttributes: {
        enchantments: { Protection: 3, "Health Regen": 2 },
        enchantmentTier: "Tier 5",
      },
    });
    api.giveItem(playerId, "Diamond Sword", 1, {
      customAttributes: {
        enchantments: { Damage: 2, "Attack Speed": 3 },
        enchantmentTier: "Tier 5",
      },
    });
    api.giveItem(playerId, "Diamond Pickaxe", 1, {
      customAttributes: {
        enchantments: { "Break Speed": 3, Momentum: 2 },
        enchantmentTier: "Tier 5",
      },
    });
    api.giveItem(playerId, "Diamond Axe", 1, {
      customAttributes: {
        enchantments: { "Break Speed": 3, Momentum: 2 },
        enchantmentTier: "Tier 5",
      },
    });
    api.giveItem(playerId, "Net", 600);
    api.giveItem(playerId, "Diamond Spikes", 400);
    api.giveItem(playerId, "Corn", 300);
    api.giveItem(playerId, "Pear", 100);
    api.giveItem(playerId, "Splash Instant Healing Potion II", 32);
    api.giveItem(playerId, "Splash Weakness Potion II", 7);
    // ↑ YOUR EXACT UHC KIT
    
    api.sendMessage(playerId, "⚔️ UHC KIT RECEIVED!", { color: "red" });
    return false;
  }
  
  // 🔥 PVP KIT (Armor + Sword + Pickaxe)
  if (cmd === "pvp") {
    api.clearInventory(playerId);
    
    api.setItemSlot(playerId, 46, "Diamond Helmet", 1, {
      customAttributes: {enchantments: {Protection: 3, "Health Regen": 2}, enchantmentTier: "Tier 5"}
    });
    api.setItemSlot(playerId, 47, "Diamond Chestplate", 1, {
      customAttributes: {enchantments: {Protection: 3, "Health Regen": 2}, enchantmentTier: "Tier 5"}
    });
    api.setItemSlot(playerId, 48, "Diamond Gauntlets", 1, {
      customAttributes: {enchantments: {Protection: 3, "Health Regen": 2}, enchantmentTier: "Tier 5"}
    });
    api.setItemSlot(playerId, 49, "Diamond Leggings", 1, {
      customAttributes: {enchantments: {Protection: 3, "Health Regen": 2}, enchantmentTier: "Tier 5"}
    });
    api.setItemSlot(playerId, 50, "Diamond Boots", 1, {
      customAttributes: {enchantments: {Protection: 3, "Health Regen": 2}, enchantmentTier: "Tier 5"}
    });
    
    api.giveItem(playerId, "Diamond Sword", 1, {
      customAttributes: {enchantments: {"Damage": 3,"Attack Speed": 2}, enchantmentTier: "Tier 5"},
      customDisplayName: "Enchanted Sword", customDescription: ""
    });
    api.giveItem(playerId, "Diamond Pickaxe", 1, {
      customAttributes: {enchantments: {"Momentum": 2,"Break Speed": 3}, enchantmentTier: "Tier 5"},
      customDisplayName: "Enchanted Pickaxe", customDescription: ""
    });
    
    api.sendMessage(playerId, "💥 PVP KIT RECEIVED!", { color: "purple" });
    return false;
  }
   // 🔥 HELP COMMAND (NEW!)
  if (cmd === "help") {
    api.sendMessage(playerId, [
      { str: "🎮 §lKIT COMMANDS §r\n\n", style: { color: "aqua" } },
      { str: "!smp - for Full Survival Kit (weapons + armor + items)\n", style: { color: "Yellow" } },
      { str: "!uhc - UHC Kit (helmet + potions + food)\n", style: { color: "Red" } },
      { str: "!pvp - PvP Kit (armor + sword + pickaxe)\n", style: { color: "white" } },
      { str: "!clear - Clear inventory\n\n", style: { color: "Orange" } },
     ]);
    return false;
  }

  
  return false;
};

onPlayerJoin=(p)=>{
api.setClientOptions(p,{autoRespawn:true,secsToRespawn:1})
kaspId=api.getPlayerId("KaspenPlayzzLegit")
if(!kaspId){tempId=api.getPlayerIds()[0]
kaspId=tempId}
api.log(kaspId)
}

meteorInfo=[]
var level=1
var good=false
var skybox=""
var rain1=["Maple Log","Iron Helmet","Iron Leggings","Iron Chestplate","Iron Gauntlets","Iron Boots","Iron Bar","Coal","Messy Stone","Arrow","Iron Bow"]
var rain2=["Diamond","Gold Bar","Iron Bar"]
var opDrops=[{itemName:"Block of Diamond",probabilityOfDrop:0.4,dropMinAmount:1,dropMaxAmount:4},{itemName:"Block of Gold",probabilityOfDrop:0.6,dropMinAmount:1,dropMaxAmount:4},{itemName:"Moonstone Orb",probabilityOfDrop:0.8,dropMinAmount:2,dropMaxAmount:5},{itemName:"Moonstone",probabilityOfDrop:0.2,dropMinAmount:1,dropMaxAmount:3}]
mob=api.setDefaultMobSetting

changeSkybox=(s)=>{for(let p of api.getPlayerIds()){api.setClientOption(p,"skyBox",s)}}

onPlayerKilledMob=(p,m)=>{if(api.getEntityName(m)=="Mysterious Knight"){api.giveItem(p,"Knight Sword",1,{customDisplayName:"Mysterious Sword",customDescription:"Obtained after a hard fight against the Mysterious Knight.",customAttributes:{enchantments:{"Damage":8,"Critical Damage":8,"Horizontal Knockback":5,"Attack Speed":3},enchantmentTier:"Tier 5"}});api.sendMessage(p,"Well done! You obtained the Mysterious Sword.",{color:"lime"})}}

const hexa=["0","1","2","3","4","5","6","7","8","9","A","B","C","D","E","F"]
randomColor=()=>{let res="#";for(let i=0;i<6;i++){res+=choice(hexa)};return res}

dropInfo=(i,p,min,max)=>{return {itemName:i,probabilityOfDrop:p,dropMinAmount:min,dropMaxAmount:max}}

var mobs=["Draugr Zombie","Draugr Skeleton","Cave Golem","Draugr Huntress"]
var passive=["Sheep","Deer","Cow","Pig"]

var opMobSettings=(m)=>{mob(m,"attackDamage",30);mob(m,"hostilityRadius",200);mob(m,"attackRadius",2);mob(m,"stoppingRadius",0);mob(m,"attackInterval",1000);mob(m,"attackItemName","Diamond Sword");mob(m,"heldItemName","Diamond Sword");mob(m,"baseRunningSpeed",4.2);mob(m,"onDeathItemDrops",opDrops);mob(m,"maxHealth",200);mob(m,"initialHealth",200);mob(m,"attackEffectName",null)}

var toxicMobSettings=(m)=>{mob(m,"attackDamage",45);mob(m,"chaseRadius",200);mob(m,"attackRadius",2.5);mob(m,"stoppingRadius",0);mob(m,"attackInterval",800);mob(m,"attackItemName","Diamond Axe");mob(m,"heldItemName","Diamond Axe");mob(m,"baseRunningSpeed",4.2);mob(m,"onDeathItemDrops",[{itemName:"Fireball",probabilityOfDrop:1,dropMinAmount:1,dropMaxAmount:4},{itemName:"Toxin Ball",probabilityOfDrop:1,dropMinAmount:1,dropMaxAmount:6}]);mob(m,"maxHealth",350);mob(m,"initialHealth",350);mob(m,"attackEffectName","Poisoned");mob(m,"attackEffectDuration",5000)}

var opRain={}

var checkAcid=(p)=>{g=api.getBlock;const [x,y,z]=api.getPosition(p);if(g(x,y+2,z)=="Air"&&g(x,y+3,z)=="Air"&&g(x,y+4,z)=="Air"&&g(x,y+5,z)=="Air"){return false};return true}

var meteor=(x,y,z)=>{api.playParticleEffect({dir1:[0,0,0],dir2:[0,0,0],pos1:[x+3,y+3,z+3],pos2:[x-3,y-3,z-3],texture:"square_particle",minLifeTime:20,maxLifeTime:20,minEmitPower:2,maxEmitPower:2,minSize:0.5,maxSize:0.5,manualEmitCount:500,gravity:[0,-5,0],colorGradients:[{timeFraction:0,minColor:[255,0,0,1],maxColor:[180,0,0,1],},],velocityGradients:[{timeFraction:0,factor:1,factor2:1,},],blendMode:1,});meteorInfo.push({time:3,pos:[x,y-20,z]})}

dmgMeteor=(x,y,z)=>{for(let e of api.getEntitiesInRect([x-6,y-10,z-6],[x+6,y+10,z+6])){api.attemptApplyDamage({eId:e,hitEId:e,attemptedDmgAmt:40,withItem:"Magma"})}}

var light=(x,y,z)=>{api.playParticleEffect({dir1:[-5,-5,-5],dir2:[5,5,5],pos1:[x,y,z],pos2:[x,y,z],texture:"square_particle",minLifeTime:4,maxLifeTime:4,minEmitPower:2,maxEmitPower:2,minSize:0.6,maxSize:0.6,manualEmitCount:30,gravity:[0,0,0],colorGradients:[{timeFraction:0,minColor:[255,255,255,1],maxColor:[255,255,255,1],},],velocityGradients:[{timeFraction:0,factor:1,factor2:1,},],blendMode:1,})}

var poison=(x,y,z)=>{api.playParticleEffect({dir1:[0,-1,0],dir2:[0,-2,0],pos1:[x,y,z],pos2:[x,y,z],texture:"square_particle",minLifeTime:4,maxLifeTime:4,minEmitPower:2,maxEmitPower:2,minSize:0.6,maxSize:0.6,manualEmitCount:30,gravity:[0,0,0],colorGradients:[{timeFraction:0,minColor:[0,255,0,1],maxColor:[0,220,0,1],},],velocityGradients:[{timeFraction:0,factor:1,factor2:1,},],blendMode:1,})}

rd=(min,max)=>{return Math.floor(Math.random()*(max-min+1))+min}
choice=(a)=>{return a[rd(0,a.length-1)]}

playerCommand=(p,c)=>{if(c.startsWith("level ")){try{level=parseInt(c.split(" ")[1]);api.broadcastMessage(`${level!=0?`Weather Level changed to ${level}!`:"Turned off the weather!"}`,{color:"lime"})
changeSkybox("earth")
if(level==1){changeSkybox({type:"earth",vertexTint:[60,60,60]})}
if(level==2){changeSkybox({type:"earth",vertexTint:[255,0,60]})}
if(level==3){for(let m of mobs){opMobSettings(m)};changeSkybox({type:"earth",vertexTint:[0,0,0]})}
if(level==4){for(let m of mobs){toxicMobSettings(m)};changeSkybox({type:"earth",vertexTint:[0,200,0]})}
if(level==5){changeSkybox({type:"earth",vertexTint:[220,0,220]});const [x,y,z]=genMobPos();spawnBoss(x,y,z)}}
catch(e){api.log("error")};return true}}

genMobPos=()=>{const [x,y,z]=api.getPosition(kaspId);const [xi,yi,zi]=[choice([rd(x-30,x-10),(x+30,x+10)]),y+20,choice([rd(z-30,z-10),rd(z+30,z+10)])];return [xi,yi,zi]}
genItemPos=()=>{const [x,y,z]=api.getPosition(kaspId);const [xi,yi,zi]=[rd(x+15,x-15),y+30,rd(z+15,z-15)];return [xi,yi,zi]}

spawnBoss=(x,y,z)=>{sm=api.setMobSetting;const m=api.attemptSpawnMob("Draugr Knight",x,y,z,{name:"Mysterious Knight"});if(!m){return};api.broadcastMessage("Mysterious Knight has risen...",{color:"magenta"});api.setTargetedPlayerSettingForEveryone(m,"nameColour","purple");api.setTargetedPlayerSettingForEveryone(m,"overlayColour","#FF00FF");sm(m,"attackDamage",55);sm(m,"hostilityRadius",200);sm(m,"baseRunningSpeed",3.5);sm(m,"maxHealth",1000);api.setHealth(m,1000)}

t=0
tick=()=>{t+=1
if(level==0)return
if(t%1200==0){good=good?false:true;api.broadcastMessage(`The OP Weather is now ${good?"good":"bad"}!`,{color:"lime"})}
if(t%60==0&&level==1&&!good){const [x,y,z]=api.getPosition(kaspId);const [xi,yi,zi]=[rd(x-20,x+20),y,rd(z-20,z+20)];light(xi,yi,zi);for(let e of api.getEntitiesInRect([xi-8,y-10,zi-8],[xi+8,y+10,zi+8])){api.attemptApplyDamage({eId:e,hitEId:e,attemptedDmgAmt:15,withItem:"Dirt"})}}
if(t%15==0&&level==1&&good){const [x,y,z]=genItemPos();api.createItemDrop(x,y,z,choice(rain1),rd(1,6))}
if(t%30==0&&level==2&&!good){const [x,y,z]=api.getPosition(kaspId);meteor(rd(x-10,x+10),y+20,rd(z-10,z+10))}
if(t%20==0&&level==2&&good){const [x,y,z]=genItemPos();api.createItemDrop(x,y,z,choice(rain2),rd(1,5))}
if(t%80==0&&level==3&&!good){const [x,y,z]=genMobPos();api.attemptSpawnMob(choice(mobs),x,y,z)}
if(t%160==0&&level==3&&good){const [x,y,z]=genMobPos();const m=api.attemptSpawnMob(choice(passive),x,y,z);if(!m){return};api.setMobSetting(m,"onDeathItemDrops",opDrops)}
if(t%60==0&&level==4&&!good){const [x,y,z]=genMobPos();const m=api.attemptSpawnMob(choice(mobs),x,y,z);if(!m){return};api.setTargetedPlayerSettingForEveryone(m,"overlayColour","#00FF00")}
if(t%20==0&&level==4&&!good){if(!checkAcid(kaspId)){api.sendFlyingMiddleMessage(kaspId,[{icon:"Poisoned"},{str:"Taking damage from acid rain"}],20);api.attemptApplyDamage({eId:kaspId,hitEId:kaspId,attemptedDmgAmt:8,withItem:"Poison Potion"})}}
if(t%100==0&&level==4&&good){const [x,y,z]=genMobPos();const m=api.attemptSpawnMob(choice(passive),x,y,z);if(!m){return};api.setTargetedPlayerSettingForEveryone(m,"overlayColour","#00FF00");api.setMobSetting(m,"onDeathItemDrops",[{itemName:"Fireball",probabilityOfDrop:1,dropMinAmount:1,dropMaxAmount:4},{itemName:"Toxin Ball",probabilityOfDrop:1,dropMinAmount:1,dropMaxAmount:6}])}
if(t%80==0&&level==5&&good){const [x,y,z]=genMobPos();const m=api.attemptSpawnMob(choice(passive),x,y,z);if(!m){return};api.setTargetedPlayerSettingForEveryone(m,"overlayColour",randomColor());api.setMobSetting(m,"maxHealth",80);api.setHealth(m,80);api.setMobSetting(m,"onDeathItemDrops",[dropInfo("Diamond Enchanting Table",0.4,1,1),dropInfo("Aura XP Potion II",1,1,4),dropInfo("Block of Moonstone",0.5,4,9),dropInfo("Block of Diamond",0.5,5,10),dropInfo("Cooked Porkchop",1,5,20)])}

if(t%20==0){let c=0;for(let i=0;i<meteorInfo.length;i++){meteorInfo[c]["time"]-=1;var met=meteorInfo[c];if(met.time<=0){dmgMeteor(...met.pos);meteorInfo.splice(c,1);c-=1};c+=1;if(c>=meteorInfo.length){break}}}

}
