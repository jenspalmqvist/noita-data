HOW TO READ:

FILE CHANGED => +++ b/biome/rainforest_dark.xml

REMOVED CODE => - background_edge_priority="10"

NEW OR CHANGED CODE => + background_edge_priority="9"

---

Actual changes below:
diff --git a/biome/\_pixel_scenes.xml b/biome/\_pixel_scenes.xml
index 49fc44a..5c53879 100644
--- a/biome/\_pixel_scenes.xml
+++ b/biome/\_pixel_scenes.xml
@@ -128,6 +128,17 @@
<PixelScene DEBUG_RELOAD_ME="0" background_filename="" clean_area_before="0" colors_filename="data/biome_impl/overworld/cliff_visual.png" material_filename="data/biome_impl/overworld/cliff.png" pos_x="-12400" pos_y="-400" skip_biome_checks="1" skip_edge_textures="0" >
</PixelScene>

-
-     <PixelScene DEBUG_RELOAD_ME="0" background_filename="" clean_area_before="0" colors_filename="data/biome_impl/eyespot_visual.png" material_filename="data/biome_impl/eyespot.png" pos_x="-3408" pos_y="1712" skip_biome_checks="1" skip_edge_textures="0" >
-     </PixelScene>
-     <PixelScene DEBUG_RELOAD_ME="0" background_filename="" clean_area_before="0" colors_filename="data/biome_impl/eyespot_visual.png" material_filename="data/biome_impl/eyespot.png" pos_x="5852" pos_y="-4944" skip_biome_checks="1" skip_edge_textures="0" >
-     </PixelScene>
-     <PixelScene DEBUG_RELOAD_ME="0" background_filename="" clean_area_before="0" colors_filename="data/biome_impl/eyespot_visual.png" material_filename="data/biome_impl/eyespot.png" pos_x="15024" pos_y="1712" skip_biome_checks="1" skip_edge_textures="0" >
-     </PixelScene>
-     <PixelScene DEBUG_RELOAD_ME="0" background_filename="" clean_area_before="0" colors_filename="data/biome_impl/eyespot_visual.png" material_filename="data/biome_impl/eyespot.png" pos_x="-1360" pos_y="9904" skip_biome_checks="1" skip_edge_textures="0" >
-     </PixelScene>
-     <PixelScene DEBUG_RELOAD_ME="0" background_filename="" clean_area_before="0" colors_filename="data/biome_impl/eyespot_visual.png" material_filename="data/biome_impl/eyespot.png" pos_x="12976" pos_y="9904" skip_biome_checks="1" skip_edge_textures="0" >
-     </PixelScene>

      <!-- just load an entity -->

@@ -192,6 +203,13 @@
<PixelScene pos_x="-12180" pos_y="-3612" just_load_an_entity="data/entities/misc/platform_wide.xml" />
<PixelScene pos_x="-12180" pos_y="-3868" just_load_an_entity="data/entities/misc/platform_wide.xml" />
<PixelScene pos_x="-12180" pos_y="-4124" just_load_an_entity="data/entities/misc/platform_wide.xml" />

-
-     <PixelScene pos_x="-3328" pos_y="1792" just_load_an_entity="data/entities/items/books/book_hint.xml" />
-     <PixelScene pos_x="-3328" pos_y="1792" just_load_an_entity="data/entities/buildings/eyespot_a.xml" />
-     <PixelScene pos_x="5932" pos_y="-4864" just_load_an_entity="data/entities/buildings/eyespot_b.xml" />
-     <PixelScene pos_x="15104" pos_y="1792" just_load_an_entity="data/entities/buildings/eyespot_c.xml" />
-     <PixelScene pos_x="-1280" pos_y="9984" just_load_an_entity="data/entities/buildings/eyespot_d.xml" />
-     <PixelScene pos_x="13056" pos_y="9984" just_load_an_entity="data/entities/buildings/eyespot_e.xml" />
 	</mBufferedPixelScenes>
 </PixelScenes>
diff --git a/biome_impl/spliced/gourd_room.png b/biome_impl/spliced/gourd_room.png
index d018205..17bd46d 100644
Binary files a/biome_impl/spliced/gourd_room.png and b/biome_impl/spliced/gourd_room.png differ
diff --git a/biome_impl/spliced/gourd_room/4.plz b/biome_impl/spliced/gourd_room/4.plz
index 0eacb04..abae6cd 100644
Binary files a/biome_impl/spliced/gourd_room/4.plz and b/biome_impl/spliced/gourd_room/4.plz differ
diff --git a/biome_impl/temple/altar_vault_capsule.png b/biome_impl/temple/altar_vault_capsule.png
index 6a3e665..947f454 100644
Binary files a/biome_impl/temple/altar_vault_capsule.png and b/biome_impl/temple/altar_vault_capsule.png differ
diff --git a/entities/_debug/debug_menu.lua b/entities/_debug/debug_menu.lua
index a296d40..917b2cb 100644
--- a/entities/_debug/debug_menu.lua
+++ b/entities/_debug/debug_menu.lua
@@ -365,7 +365,7 @@ main_menu_items =
 		end,
 	},
 	{

*     ui_name="Convert material",

-     ui_name="Fungal shift",
  action = function()
  local x, y = GameGetCameraPos()
  local player_entity = EntityGetClosestWithTag( x, y, "player_unit" )
  @@ -375,6 +375,18 @@ main_menu_items =
  fungal_shift( player_entity, x, y, true )
  end,
  },
- {
-     ui_name="Fungal shift lava->water",
-     action = function()
-     	ConvertMaterialEverywhere( CellFactory_GetType( "lava" ), CellFactory_GetType( "water" ) )
-     end
- },
- {
-     ui_name="Fungal shift lava->radioactive_liquid",
-     action = function()
-     	ConvertMaterialEverywhere( CellFactory_GetType( "lava" ), CellFactory_GetType( "radioactive_liquid" ) )
-     end
- },
  {
  ui_name="ConvertMaterialOnAreaInstantly() - test near camera",
  action = function()
  diff --git a/entities/animals/apparition/playerghost.xml b/entities/animals/apparition/playerghost.xml
  index bca3e8f..00a50b8 100644
  --- a/entities/animals/apparition/playerghost.xml
  +++ b/entities/animals/apparition/playerghost.xml
  @@ -22,6 +22,8 @@
  </AudioLoopComponent>
  <Entity>
-     <InheritTransformComponent />
- <GameEffectComponent
  effect="PROTECTION_FREEZE"
  frames="-1"
  diff --git a/entities/animals/assassin.xml b/entities/animals/assassin.xml
  index 15bcc70..b0d0c75 100644
  --- a/entities/animals/assassin.xml
  +++ b/entities/animals/assassin.xml
  @@ -134,6 +134,8 @@
  </AudioLoopComponent>
  <Entity>
-     <InheritTransformComponent />
- <GameEffectComponent
  effect="PROTECTION_FREEZE"
  frames="-1"
  diff --git a/entities/animals/boss_alchemist/boss_alchemist.xml b/entities/animals/boss_alchemist/boss_alchemist.xml
  index 1ac6f02..21dca17 100644
  --- a/entities/animals/boss_alchemist/boss_alchemist.xml
  +++ b/entities/animals/boss_alchemist/boss_alchemist.xml
  @@ -181,6 +181,8 @@
  </VariableStorageComponent>
  <Entity>
-     <InheritTransformComponent />
- <GameEffectComponent
  effect="PROTECTION_FREEZE"
  frames="-1"
  @@ -189,6 +191,8 @@
  </Entity>
  <Entity>
-     <InheritTransformComponent />
- <GameEffectComponent
  effect="PROTECTION*ELECTRICITY"
  frames="-1"
  diff --git a/entities/animals/boss_centipede/sampo_init.lua b/entities/animals/boss_centipede/sampo_init.lua
  index 358661f..e84b99a 100644
  --- a/entities/animals/boss_centipede/sampo_init.lua
  +++ b/entities/animals/boss_centipede/sampo_init.lua
  @@ -10,7 +10,7 @@ if( orb_count > MAX_ORB_NAMES ) then orb_count = MAX_ORB_NAMES end
  local orb_name = "$item_mcguffin*" .. tostring(orb*count)
  local orb_desc = "$itemdesc_mcguffin*" .. tostring(orb_count)

-if( GameGetOrbCountThisRun() > 33 ) then
+if( GameGetOrbCountThisRun() >= 33 ) then
orb_name = "$item_mcguffin_33"
 	orb_desc = "$itemdesc_mcguffin_33"
end
diff --git a/entities/animals/boss_ghost/boss_ghost.xml b/entities/animals/boss_ghost/boss_ghost.xml
index 2faabdd..6f39de7 100644
--- a/entities/animals/boss_ghost/boss_ghost.xml
+++ b/entities/animals/boss_ghost/boss_ghost.xml
@@ -390,6 +390,8 @@
</HealthBarComponent>
<Entity>

-     <InheritTransformComponent />
- <GameEffectComponent
  effect="PROTECTION_FREEZE"
  frames="-1"
  @@ -398,6 +400,8 @@
  </Entity>
  <Entity>
-     <InheritTransformComponent />
- <GameEffectComponent
  effect="PROTECTION_ELECTRICITY"
  frames="-1"
  diff --git a/entities/animals/boss_ghost/polyp_shot.xml b/entities/animals/boss_ghost/polyp_shot.xml
  index 4128a58..5b860ee 100644
  --- a/entities/animals/boss_ghost/polyp_shot.xml
  +++ b/entities/animals/boss_ghost/polyp_shot.xml
  @@ -1,4 +1,4 @@ -<Entity tags="hittable,resist_repulsion" name="$boss_ghost_polyp" > +<Entity tags="hittable,resist_repulsion" name="$animal_boss_ghost_polyp" >
   	<Base file="data/entities/base_projectile.xml" >
   		<VelocityComponent
  diff --git a/entities/animals/boss_pit/boss_pit.xml b/entities/animals/boss_pit/boss_pit.xml
  index 8c053ed..6fa2c0e 100644
  --- a/entities/animals/boss_pit/boss_pit.xml
  +++ b/entities/animals/boss_pit/boss_pit.xml
  @@ -292,6 +292,8 @@
   	<Entity><Base file="data/entities/animals/boss_pit/tentacle.xml"> <InheritTransformComponent><Transform position.x="0"  position.y="4" ></Transform></InheritTransformComponent> </Base></Entity>
   	
   	<Entity>
-     <InheritTransformComponent />
- <GameEffectComponent
  effect="PROTECTION_FREEZE"
  frames="-1"
  @@ -300,6 +302,8 @@
  </Entity>
  <Entity>
-     <InheritTransformComponent />
- <GameEffectComponent
  effect="PROTECTION_ELECTRICITY"
  frames="-1"
  diff --git a/entities/animals/boss_wizard/boss_wizard.xml b/entities/animals/boss_wizard/boss_wizard.xml
  index af39edb..80ec5ee 100644
  --- a/entities/animals/boss_wizard/boss_wizard.xml
  +++ b/entities/animals/boss_wizard/boss_wizard.xml
  @@ -261,6 +261,8 @@
  </LuaComponent>
  <Entity>
-     <InheritTransformComponent />
- <GameEffectComponent
  effect="PROTECTION_FREEZE"
  frames="-1"
  @@ -269,6 +271,8 @@
  </Entity>
  <Entity>
-     <InheritTransformComponent />
- <GameEffectComponent
  effect="PROTECTION_ELECTRICITY"
  frames="-1"
  @@ -277,6 +281,8 @@
  </Entity>
  <Entity>
-     <InheritTransformComponent />
- <GameEffectComponent
  effect="PROTECTION_ALL"
  frames="101"
  diff --git a/entities/animals/boss_wizard/wizard_orb_blood.xml b/entities/animals/boss_wizard/wizard_orb_blood.xml
  index 2c50a61..cf21465 100644
  --- a/entities/animals/boss_wizard/wizard_orb_blood.xml
  +++ b/entities/animals/boss_wizard/wizard_orb_blood.xml
  @@ -89,6 +89,8 @@
  </DamageModelComponent>
  <Entity>
-     <InheritTransformComponent />
- <GameEffectComponent
  effect="PROTECTION_FREEZE"
  frames="-1"
  @@ -97,6 +99,8 @@
  </Entity>
  <Entity>
-     <InheritTransformComponent />
- <GameEffectComponent
  effect="PROTECTION_ELECTRICITY"
  frames="-1"
  diff --git a/entities/animals/boss_wizard/wizard_orb_death.xml b/entities/animals/boss_wizard/wizard_orb_death.xml
  index b13219b..071af17 100644
  --- a/entities/animals/boss_wizard/wizard_orb_death.xml
  +++ b/entities/animals/boss_wizard/wizard_orb_death.xml
  @@ -89,6 +89,8 @@
  </DamageModelComponent>
  <Entity>
-     <InheritTransformComponent />
- <GameEffectComponent
  effect="PROTECTION_FREEZE"
  frames="-1"
  @@ -97,6 +99,8 @@
  </Entity>
  <Entity>
-     <InheritTransformComponent />
- <GameEffectComponent
  effect="PROTECTION_ELECTRICITY"
  frames="-1"
  diff --git a/entities/animals/crypt/phantom_a.xml b/entities/animals/crypt/phantom_a.xml
  index a171003..7b71d6c 100644
  --- a/entities/animals/crypt/phantom_a.xml
  +++ b/entities/animals/crypt/phantom_a.xml
  @@ -8,6 +8,8 @@
     </Base>

   <Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/crypt/phantom_b.xml b/entities/animals/crypt/phantom_b.xml
index d40e1ce..6a7e901 100644
--- a/entities/animals/crypt/phantom_b.xml
+++ b/entities/animals/crypt/phantom_b.xml
@@ -8,6 +8,8 @@
   </Base>
   
   <Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/crypt/wizard_neutral.xml b/entities/animals/crypt/wizard_neutral.xml
index 27b09e9..b1f5f05 100644
--- a/entities/animals/crypt/wizard_neutral.xml
+++ b/entities/animals/crypt/wizard_neutral.xml
@@ -17,6 +17,8 @@
     </Entity>
   
   <Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
@@ -25,6 +27,8 @@
 	</Entity>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_ELECTRICITY"
 	        frames="-1"
diff --git a/entities/animals/crypt/worm_skull.xml b/entities/animals/crypt/worm_skull.xml
index ee5b54b..bdacdd6 100644
--- a/entities/animals/crypt/worm_skull.xml
+++ b/entities/animals/crypt/worm_skull.xml
@@ -7,6 +7,8 @@
   </Base>
   
   <Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/drone.xml b/entities/animals/drone.xml
index 149e600..d7303cc 100644
--- a/entities/animals/drone.xml
+++ b/entities/animals/drone.xml
@@ -93,6 +93,8 @@
 	</AudioLoopComponent>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/drone_lasership.xml b/entities/animals/drone_lasership.xml
index 96e8346..3368147 100644
--- a/entities/animals/drone_lasership.xml
+++ b/entities/animals/drone_lasership.xml
@@ -120,6 +120,8 @@
 	</AudioLoopComponent>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/drone_physics.xml b/entities/animals/drone_physics.xml
index bb4fa65..87861b7 100644
--- a/entities/animals/drone_physics.xml
+++ b/entities/animals/drone_physics.xml
@@ -183,6 +183,8 @@
 	</AudioLoopComponent>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/drone_shield.xml b/entities/animals/drone_shield.xml
index 5a2b931..a356bcc 100644
--- a/entities/animals/drone_shield.xml
+++ b/entities/animals/drone_shield.xml
@@ -107,6 +107,8 @@
 	</AudioLoopComponent>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/giant.xml b/entities/animals/giant.xml
index fb734d9..5d6a998 100644
--- a/entities/animals/giant.xml
+++ b/entities/animals/giant.xml
@@ -37,6 +37,7 @@
 			ragdoll_blood_amount_absolute="0"
 			blood_sprite_directional="data/particles/bloodsplatters/bloodsplatter_directional_blue_$[1-3].xml"
 			blood_sprite_large="data/particles/bloodsplatters/bloodsplatter_blue_$[1-3].xml"
+			healing_particle_effect_entity="data/entities/particles/heal_effect.xml"
 			>
 			<damage_multipliers
 				explosion="0.2"
diff --git a/entities/animals/healerdrone_physics.xml b/entities/animals/healerdrone_physics.xml
index 2626f8d..18e4da8 100644
--- a/entities/animals/healerdrone_physics.xml
+++ b/entities/animals/healerdrone_physics.xml
@@ -180,6 +180,8 @@
 	</Base>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/icer.xml b/entities/animals/icer.xml
index 5b68600..26ab1cb 100644
--- a/entities/animals/icer.xml
+++ b/entities/animals/icer.xml
@@ -153,6 +153,8 @@
     </ItemPickUpperComponent>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/missilecrab.xml b/entities/animals/missilecrab.xml
index b1f0f0d..0d37112 100644
--- a/entities/animals/missilecrab.xml
+++ b/entities/animals/missilecrab.xml
@@ -128,6 +128,8 @@
 	</SpriteComponent>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/monk.xml b/entities/animals/monk.xml
index 3b6b108..a196f65 100644
--- a/entities/animals/monk.xml
+++ b/entities/animals/monk.xml
@@ -130,6 +130,8 @@
 	</AudioComponent>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/necrobot.xml b/entities/animals/necrobot.xml
index 9949e46..81010bd 100644
--- a/entities/animals/necrobot.xml
+++ b/entities/animals/necrobot.xml
@@ -141,6 +141,8 @@
 	</AudioComponent>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/necrobot_super.xml b/entities/animals/necrobot_super.xml
index e9b1c14..de2085d 100644
--- a/entities/animals/necrobot_super.xml
+++ b/entities/animals/necrobot_super.xml
@@ -141,6 +141,8 @@
 	</AudioComponent>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/necromancer_super.xml b/entities/animals/necromancer_super.xml
index 23cd528..628a488 100644
--- a/entities/animals/necromancer_super.xml
+++ b/entities/animals/necromancer_super.xml
@@ -182,13 +182,18 @@
 
 	<!-- protections -->
 	<Entity>
+		<InheritTransformComponent />
+		
         <GameEffectComponent 
             effect="PROTECTION_FREEZE"
             frames="-1"
         >
         </GameEffectComponent >
     </Entity>
+	
     <Entity>
+		<InheritTransformComponent />
+		
         <GameEffectComponent 
             effect="PROTECTION_ELECTRICITY"
             frames="-1"
diff --git a/entities/animals/parallel/alchemist/parallel_alchemist.xml b/entities/animals/parallel/alchemist/parallel_alchemist.xml
index b78000b..dd569a9 100644
--- a/entities/animals/parallel/alchemist/parallel_alchemist.xml
+++ b/entities/animals/parallel/alchemist/parallel_alchemist.xml
@@ -176,6 +176,8 @@
 	</VariableStorageComponent>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
@@ -184,6 +186,8 @@
 	</Entity>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_ELECTRICITY"
 	        frames="-1"
diff --git a/entities/animals/parallel/tentacles/parallel_tentacles.xml b/entities/animals/parallel/tentacles/parallel_tentacles.xml
index b9627fb..327f3c6 100644
--- a/entities/animals/parallel/tentacles/parallel_tentacles.xml
+++ b/entities/animals/parallel/tentacles/parallel_tentacles.xml
@@ -246,6 +246,8 @@
 	<Entity><Base file="data/entities/animals/parallel/tentacles/tentacle.xml"> <InheritTransformComponent><Transform position.x="0"  position.y="4" ></Transform></InheritTransformComponent> </Base></Entity>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
@@ -254,6 +256,8 @@
 	</Entity>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_ELECTRICITY"
 	        frames="-1"
diff --git a/entities/animals/pebble_physics.xml b/entities/animals/pebble_physics.xml
index 173dfd2..a00709a 100644
--- a/entities/animals/pebble_physics.xml
+++ b/entities/animals/pebble_physics.xml
@@ -58,6 +58,7 @@
 			blood_spray_material="blood_cold"
 			blood_sprite_directional="data/particles/bloodsplatters/bloodsplatter_directional_blue_$[1-3].xml"
 			blood_sprite_large="data/particles/bloodsplatters/bloodsplatter_blue_$[1-3].xml"
+			healing_particle_effect_entity="data/entities/particles/heal_effect.xml"
 			>
 			<damage_multipliers
 				melee="0.0"
diff --git a/entities/animals/phantom_a.xml b/entities/animals/phantom_a.xml
index 5789428..24aff3b 100644
--- a/entities/animals/phantom_a.xml
+++ b/entities/animals/phantom_a.xml
@@ -124,6 +124,8 @@
 	</AudioLoopComponent>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/phantom_b.xml b/entities/animals/phantom_b.xml
index e5fd6cf..0f4c303 100644
--- a/entities/animals/phantom_b.xml
+++ b/entities/animals/phantom_b.xml
@@ -124,6 +124,8 @@
 	</AudioLoopComponent>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/playerghost.xml b/entities/animals/playerghost.xml
index 417b83d..45656b7 100644
--- a/entities/animals/playerghost.xml
+++ b/entities/animals/playerghost.xml
@@ -28,6 +28,8 @@
 	</AudioLoopComponent>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/roboguard.xml b/entities/animals/roboguard.xml
index 1583f18..ca65d45 100644
--- a/entities/animals/roboguard.xml
+++ b/entities/animals/roboguard.xml
@@ -92,6 +92,8 @@
 
 	<!-- protection from FREEZING -->
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/spearbot.xml b/entities/animals/spearbot.xml
index 18a8556..17983d4 100644
--- a/entities/animals/spearbot.xml
+++ b/entities/animals/spearbot.xml
@@ -132,6 +132,8 @@
 	</AudioComponent>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
@@ -140,6 +142,8 @@
 	</Entity>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_EXPLOSION"
 	        frames="-1"
diff --git a/entities/animals/tank.xml b/entities/animals/tank.xml
index d3d914c..ed2c36e 100644
--- a/entities/animals/tank.xml
+++ b/entities/animals/tank.xml
@@ -205,6 +205,8 @@
 
 	<!-- protection from FREEZING -->
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/tank_rocket.xml b/entities/animals/tank_rocket.xml
index 26a448d..4ba9d0d 100644
--- a/entities/animals/tank_rocket.xml
+++ b/entities/animals/tank_rocket.xml
@@ -206,6 +206,8 @@
 	</AudioLoopComponent>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/tank_super.xml b/entities/animals/tank_super.xml
index 852addf..7152d09 100644
--- a/entities/animals/tank_super.xml
+++ b/entities/animals/tank_super.xml
@@ -204,6 +204,8 @@
 	
 	<!-- protection from FREEZING -->
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/the_end/spearbot.xml b/entities/animals/the_end/spearbot.xml
index d09bcd2..3ff6ce7 100644
--- a/entities/animals/the_end/spearbot.xml
+++ b/entities/animals/the_end/spearbot.xml
@@ -8,6 +8,8 @@
   </Base>
   
   <Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
@@ -16,6 +18,8 @@
 	</Entity>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_EXPLOSION"
 	        frames="-1"
diff --git a/entities/animals/thundermage_big.xml b/entities/animals/thundermage_big.xml
index 4526784..cb2de8d 100644
--- a/entities/animals/thundermage_big.xml
+++ b/entities/animals/thundermage_big.xml
@@ -165,6 +165,8 @@
 	</AudioLoopComponent>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
@@ -173,6 +175,8 @@
 	</Entity>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_ELECTRICITY"
 	        frames="-1"
diff --git a/entities/animals/turret_left.xml b/entities/animals/turret_left.xml
index 10f92fd..c831f97 100644
--- a/entities/animals/turret_left.xml
+++ b/entities/animals/turret_left.xml
@@ -9,6 +9,8 @@
 	</Base>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/turret_right.xml b/entities/animals/turret_right.xml
index a698318..66499a0 100644
--- a/entities/animals/turret_right.xml
+++ b/entities/animals/turret_right.xml
@@ -176,6 +176,8 @@
 	</SpriteComponent>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/vault/assassin.xml b/entities/animals/vault/assassin.xml
index ff39ec8..6982f47 100644
--- a/entities/animals/vault/assassin.xml
+++ b/entities/animals/vault/assassin.xml
@@ -13,6 +13,8 @@
 	</Entity>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/vault/drone_physics.xml b/entities/animals/vault/drone_physics.xml
index 5e567eb..eff2e99 100644
--- a/entities/animals/vault/drone_physics.xml
+++ b/entities/animals/vault/drone_physics.xml
@@ -18,6 +18,8 @@
 	</Entity>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/vault/healerdrone_physics.xml b/entities/animals/vault/healerdrone_physics.xml
index 3b30353..6001ac4 100644
--- a/entities/animals/vault/healerdrone_physics.xml
+++ b/entities/animals/vault/healerdrone_physics.xml
@@ -20,6 +20,8 @@
   </Base>
   
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/vault/icer.xml b/entities/animals/vault/icer.xml
index 56a6595..6cea79e 100644
--- a/entities/animals/vault/icer.xml
+++ b/entities/animals/vault/icer.xml
@@ -8,6 +8,8 @@
   </Base>
   
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/vault/missilecrab.xml b/entities/animals/vault/missilecrab.xml
index f0f2fa0..dae40ec 100644
--- a/entities/animals/vault/missilecrab.xml
+++ b/entities/animals/vault/missilecrab.xml
@@ -8,6 +8,8 @@
   </Base>
   
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/vault/roboguard.xml b/entities/animals/vault/roboguard.xml
index 05ae0f2..3faf715 100644
--- a/entities/animals/vault/roboguard.xml
+++ b/entities/animals/vault/roboguard.xml
@@ -8,6 +8,8 @@
   </Base>
   
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/vault/tank.xml b/entities/animals/vault/tank.xml
index cbe21e6..5ce9d07 100644
--- a/entities/animals/vault/tank.xml
+++ b/entities/animals/vault/tank.xml
@@ -8,6 +8,8 @@
   </Base>
   
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/vault/tank_rocket.xml b/entities/animals/vault/tank_rocket.xml
index 39ad3c5..58907b0 100644
--- a/entities/animals/vault/tank_rocket.xml
+++ b/entities/animals/vault/tank_rocket.xml
@@ -8,6 +8,8 @@
   </Base>
   
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/vault/tank_super.xml b/entities/animals/vault/tank_super.xml
index 876c945..d7f00bd 100644
--- a/entities/animals/vault/tank_super.xml
+++ b/entities/animals/vault/tank_super.xml
@@ -205,6 +205,8 @@
 	</AudioLoopComponent>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/vault/turret_left.xml b/entities/animals/vault/turret_left.xml
index e077c8c..b18ddab 100644
--- a/entities/animals/vault/turret_left.xml
+++ b/entities/animals/vault/turret_left.xml
@@ -8,6 +8,8 @@
   </Base>
   
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/vault/turret_right.xml b/entities/animals/vault/turret_right.xml
index 90a5f9d..b4cad8c 100644
--- a/entities/animals/vault/turret_right.xml
+++ b/entities/animals/vault/turret_right.xml
@@ -8,6 +8,8 @@
   </Base>
   
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/wizard_neutral.xml b/entities/animals/wizard_neutral.xml
index 63900be..586e380 100644
--- a/entities/animals/wizard_neutral.xml
+++ b/entities/animals/wizard_neutral.xml
@@ -166,6 +166,8 @@
 	</SpriteComponent>
     
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
@@ -174,6 +176,8 @@
 	</Entity>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_ELECTRICITY"
 	        frames="-1"
diff --git a/entities/animals/wizard_wither.xml b/entities/animals/wizard_wither.xml
index e0556c5..120595f 100644
--- a/entities/animals/wizard_wither.xml
+++ b/entities/animals/wizard_wither.xml
@@ -111,6 +111,8 @@
     </Entity>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/animals/worm_skull.xml b/entities/animals/worm_skull.xml
index 2bb43ad..d87800f 100644
--- a/entities/animals/worm_skull.xml
+++ b/entities/animals/worm_skull.xml
@@ -342,6 +342,8 @@
   </AudioComponent>
   
   <Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/buildings/arrowtrap_left.xml b/entities/buildings/arrowtrap_left.xml
index 9e74332..3b2acde 100644
--- a/entities/buildings/arrowtrap_left.xml
+++ b/entities/buildings/arrowtrap_left.xml
@@ -86,6 +86,8 @@
 	</CameraBoundComponent>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 		<GameEffectComponent 
 			effect="PROTECTION_FREEZE"
 			frames="-1"
@@ -94,6 +96,8 @@
 	</Entity>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 		<GameEffectComponent 
 			effect="PROTECTION_ELECTRICITY"
 			frames="-1"
diff --git a/entities/buildings/arrowtrap_right.xml b/entities/buildings/arrowtrap_right.xml
index a4e56e2..735c73a 100644
--- a/entities/buildings/arrowtrap_right.xml
+++ b/entities/buildings/arrowtrap_right.xml
@@ -27,6 +27,8 @@
 	</Base>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 		<GameEffectComponent 
 			effect="PROTECTION_FREEZE"
 			frames="-1"
@@ -35,6 +37,8 @@
 	</Entity>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 		<GameEffectComponent 
 			effect="PROTECTION_ELECTRICITY"
 			frames="-1"
diff --git a/entities/buildings/failed_alchemist_orb.xml b/entities/buildings/failed_alchemist_orb.xml
index c5bdd6b..cd3e581 100644
--- a/entities/buildings/failed_alchemist_orb.xml
+++ b/entities/buildings/failed_alchemist_orb.xml
@@ -88,6 +88,8 @@
   </AudioLoopComponent>
   
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_ELECTRICITY"
 	        frames="-1"
@@ -96,6 +98,8 @@
 	</Entity>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
diff --git a/entities/buildings/firetrap_left.xml b/entities/buildings/firetrap_left.xml
index 0c03236..ec543d9 100644
--- a/entities/buildings/firetrap_left.xml
+++ b/entities/buildings/firetrap_left.xml
@@ -87,6 +87,8 @@
 	</CameraBoundComponent>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
@@ -95,6 +97,8 @@
 	</Entity>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_ELECTRICITY"
 	        frames="-1"
diff --git a/entities/buildings/firetrap_right.xml b/entities/buildings/firetrap_right.xml
index e067b97..d9610ef 100644
--- a/entities/buildings/firetrap_right.xml
+++ b/entities/buildings/firetrap_right.xml
@@ -27,6 +27,8 @@
 	</Base>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
@@ -35,6 +37,8 @@
 	</Entity>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_ELECTRICITY"
 	        frames="-1"
diff --git a/entities/buildings/spittrap_left.xml b/entities/buildings/spittrap_left.xml
index ed65c5d..3c2bc00 100644
--- a/entities/buildings/spittrap_left.xml
+++ b/entities/buildings/spittrap_left.xml
@@ -87,6 +87,8 @@
 	</CameraBoundComponent>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
@@ -95,6 +97,8 @@
 	</Entity>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_ELECTRICITY"
 	        frames="-1"
diff --git a/entities/buildings/spittrap_right.xml b/entities/buildings/spittrap_right.xml
index c68359f..085257c 100644
--- a/entities/buildings/spittrap_right.xml
+++ b/entities/buildings/spittrap_right.xml
@@ -27,6 +27,8 @@
 	</Base>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
@@ -35,6 +37,8 @@
 	</Entity>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_ELECTRICITY"
 	        frames="-1"
diff --git a/entities/buildings/thundertrap_left.xml b/entities/buildings/thundertrap_left.xml
index 0c5ba81..8d8e4e0 100644
--- a/entities/buildings/thundertrap_left.xml
+++ b/entities/buildings/thundertrap_left.xml
@@ -87,6 +87,8 @@
 	</CameraBoundComponent>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
@@ -95,6 +97,8 @@
 	</Entity>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_ELECTRICITY"
 	        frames="-1"
diff --git a/entities/buildings/thundertrap_right.xml b/entities/buildings/thundertrap_right.xml
index 0d30c04..6f99321 100644
--- a/entities/buildings/thundertrap_right.xml
+++ b/entities/buildings/thundertrap_right.xml
@@ -27,6 +27,8 @@
 	</Base>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_FREEZE"
 	        frames="-1"
@@ -35,6 +37,8 @@
 	</Entity>
 	
 	<Entity>
+		<InheritTransformComponent />
+		
 	    <GameEffectComponent 
 	        effect="PROTECTION_ELECTRICITY"
 	        frames="-1"
diff --git a/entities/buildings/vault_lab_puzzle_worm.xml b/entities/buildings/vault_lab_puzzle_worm.xml
index d539920..a2ecc6b 100644
--- a/entities/buildings/vault_lab_puzzle_worm.xml
+++ b/entities/buildings/vault_lab_puzzle_worm.xml
@@ -2,7 +2,7 @@
 	<Base file="data/entities/buildings/vault_lab_puzzle_protect.xml">
 		<MaterialAreaCheckerComponent
 			material="magic_liquid_worm_attractor"
-			material2="magic_liquid_worm_attractor" >
+			material2="blood_worm" >
 		</MaterialAreaCheckerComponent>
 		<PixelSceneComponent
 			pixel_scene_background="data/biome_impl/vault/lab_puzzle_worm_background.png" >
diff --git a/entities/items/pickup/bloodmoney_10.xml b/entities/items/pickup/bloodmoney_10.xml
index 0d1dbb8..97d8732 100644
--- a/entities/items/pickup/bloodmoney_10.xml
+++ b/entities/items/pickup/bloodmoney_10.xml
@@ -22,6 +22,7 @@
 	<!-- Arvi: Increased this to 0.16 so that 10 hp nuggets are a bit better at healing relative to the others -->
 	
 	<VariableStorageComponent
+		_tags="enabled_in_world"
 		name="hp_value"
 		value_float="0.16" >
 	</VariableStorageComponent>
diff --git a/entities/items/pickup/bloodmoney_1000.xml b/entities/items/pickup/bloodmoney_1000.xml
index d01e970..af57ec5 100644
--- a/entities/items/pickup/bloodmoney_1000.xml
+++ b/entities/items/pickup/bloodmoney_1000.xml
@@ -20,6 +20,7 @@
 
 	<!-- 3*100 / 25 = 12.0 -->
 	<VariableStorageComponent
+		_tags="enabled_in_world"
 		name="hp_value"
 		value_float="0.6" >
 	</VariableStorageComponent>
diff --git a/entities/items/pickup/bloodmoney_10000.xml b/entities/items/pickup/bloodmoney_10000.xml
index f6bd3e2..57fd540 100644
--- a/entities/items/pickup/bloodmoney_10000.xml
+++ b/entities/items/pickup/bloodmoney_10000.xml
@@ -20,6 +20,7 @@
 
 	<!-- 3*100 / 25 = 12.0 -->
 	<VariableStorageComponent
+		_tags="enabled_in_world"
 		name="hp_value"
 		value_float="0.6" >
 	</VariableStorageComponent>
diff --git a/entities/items/pickup/bloodmoney_200.xml b/entities/items/pickup/bloodmoney_200.xml
index 30d20d4..0d3befe 100644
--- a/entities/items/pickup/bloodmoney_200.xml
+++ b/entities/items/pickup/bloodmoney_200.xml
@@ -20,6 +20,7 @@
 
 	<!-- 3*20 / 25 = 0.6 -->
 	<VariableStorageComponent
+		_tags="enabled_in_world"
 		name="hp_value"
 		value_float="0.6" >
 	</VariableStorageComponent>
diff --git a/entities/items/pickup/bloodmoney_50.xml b/entities/items/pickup/bloodmoney_50.xml
index 11cd309..60eace3 100644
--- a/entities/items/pickup/bloodmoney_50.xml
+++ b/entities/items/pickup/bloodmoney_50.xml
@@ -20,6 +20,7 @@
 
 	<!-- 3*5 / 25 = 0.6 -->
 	<VariableStorageComponent
+		_tags="enabled_in_world"
 		name="hp_value"
 		value_float="0.4" >
 	</VariableStorageComponent>
diff --git a/entities/items/pickup/goldnugget.xml b/entities/items/pickup/goldnugget.xml
index f988d5b..f2b64eb 100644
--- a/entities/items/pickup/goldnugget.xml
+++ b/entities/items/pickup/goldnugget.xml
@@ -2,6 +2,7 @@
 
 	<!-- physical presence -->
 	<UIInfoComponent
+		_tags="enabled_in_world"
 		name="$item_goldnugget">
 	</UIInfoComponent>
 
@@ -18,7 +19,8 @@
 		on_death_leave_physics_body="1" >
 	</PhysicsBodyComponent>
 	
-	<PhysicsImageShapeComponent 
+	<PhysicsImageShapeComponent
+		_tags="enabled_in_world"
 		body_id="1"
 		centered="1"
 		image_file="data/items_gfx/goldnugget_01.png"
@@ -26,6 +28,7 @@
 	</PhysicsImageShapeComponent>
 
 	<VariableStorageComponent
+		_tags="enabled_in_world"
 		name="gold_value"
 		value_int="10" >
 	</VariableStorageComponent>
@@ -55,14 +58,17 @@
 	</HitboxComponent>
 
 	<LifetimeComponent
+		_tags="enabled_in_world"
 		lifetime="900" >
 	</LifetimeComponent>
 	
-	<LuaComponent 
+	<LuaComponent
+		_tags="enabled_in_world"
 		script_item_picked_up="data/scripts/items/gold_pickup.lua" >
 	</LuaComponent>
 	
-	<LuaComponent 
+	<LuaComponent
+		_tags="enabled_in_world"
 		script_source_file="data/scripts/perks/gold_explosion.lua" 
 		execute_on_added="1"
 		remove_after_executed="1"
@@ -71,6 +77,7 @@
 
 	<!-- particle glitter -->
 	<SpriteParticleEmitterComponent
+		_tags="enabled_in_world"
 		sprite_file="data/particles/shine_08.xml"
 		lifetime="0.2"
 		randomize_lifetime.min="0.1"
diff --git a/entities/items/pickup/goldnugget_10.xml b/entities/items/pickup/goldnugget_10.xml
index 9f7c3f2..c8203ad 100644
--- a/entities/items/pickup/goldnugget_10.xml
+++ b/entities/items/pickup/goldnugget_10.xml
@@ -2,10 +2,11 @@
 
 	<!-- physical presence -->
 	<UIInfoComponent
+		_tags="enabled_in_world"
 		name="$item_goldnugget">
 	</UIInfoComponent>
 
-	<PhysicsBodyComponent 
+	<PhysicsBodyComponent
 		_tags="enabled_in_world"
 		uid="1" 
 		allow_sleep="1" 
@@ -18,7 +19,8 @@
 		on_death_leave_physics_body="1" >
 	</PhysicsBodyComponent>
 	
-	<PhysicsImageShapeComponent 
+	<PhysicsImageShapeComponent
+		_tags="enabled_in_world"
 		body_id="1"
 		centered="1"
 		image_file="data/items_gfx/goldnugget_6px.png"
@@ -26,6 +28,7 @@
 	</PhysicsImageShapeComponent>
 
 	<VariableStorageComponent
+		_tags="enabled_in_world"
 		name="gold_value"
 		value_int="10" >
 	</VariableStorageComponent>
@@ -55,14 +58,17 @@
 	</HitboxComponent>
 
 	<LifetimeComponent
+		_tags="enabled_in_world"
 		lifetime="900" >
 	</LifetimeComponent>
 	
-	<LuaComponent 
+	<LuaComponent
+		_tags="enabled_in_world"
 		script_item_picked_up="data/scripts/items/gold_pickup.lua" >
 	</LuaComponent>
 	
-	<LuaComponent 
+	<LuaComponent
+		_tags="enabled_in_world"
 		script_source_file="data/scripts/perks/gold_explosion.lua" 
 		execute_on_added="1"
 		remove_after_executed="1"
@@ -71,6 +77,7 @@
 
 	<!-- particle glitter -->
 	<SpriteParticleEmitterComponent
+		_tags="enabled_in_world"
 		sprite_file="data/particles/shine_08.xml"
 		lifetime="0.2"
 		randomize_lifetime.min="0.1"
diff --git a/entities/items/pickup/goldnugget_1000.xml b/entities/items/pickup/goldnugget_1000.xml
index 852a034..e718ced 100644
--- a/entities/items/pickup/goldnugget_1000.xml
+++ b/entities/items/pickup/goldnugget_1000.xml
@@ -2,10 +2,11 @@
 
 	<!-- physical presence -->
 	<UIInfoComponent
+		_tags="enabled_in_world"
 		name="$item_goldnugget">
 	</UIInfoComponent>
 
-	<PhysicsBodyComponent 
+	<PhysicsBodyComponent
 		_tags="enabled_in_world"
 		uid="1" 
 		allow_sleep="1" 
@@ -18,7 +19,8 @@
 		on_death_leave_physics_body="1" >
 	</PhysicsBodyComponent>
 	
-	<PhysicsImageShapeComponent 
+	<PhysicsImageShapeComponent
+		_tags="enabled_in_world"
 		body_id="1"
 		centered="1"
 		image_file="data/items_gfx/goldnugget_20px.png"
@@ -26,6 +28,7 @@
 	</PhysicsImageShapeComponent>
 
 	<VariableStorageComponent
+		_tags="enabled_in_world"
 		name="gold_value"
 		value_int="1000" >
 	</VariableStorageComponent>
@@ -55,14 +58,17 @@
 	</HitboxComponent>
 
 	<LifetimeComponent
+		_tags="enabled_in_world"
 		lifetime="900" >
 	</LifetimeComponent>
 	
-	<LuaComponent 
+	<LuaComponent
+		_tags="enabled_in_world"
 		script_item_picked_up="data/scripts/items/gold_pickup.lua" >
 	</LuaComponent>
 	
-	<LuaComponent 
+	<LuaComponent
+		_tags="enabled_in_world"
 		script_source_file="data/scripts/perks/gold_explosion.lua" 
 		execute_on_added="1"
 		remove_after_executed="1"
@@ -71,6 +77,7 @@
 
 	<!-- particle glitter -->
 	<SpriteParticleEmitterComponent
+		_tags="enabled_in_world"
 		sprite_file="data/particles/shine_07.xml"
 		lifetime="0.3"
 		emission_interval_min_frames="20"
@@ -96,6 +103,7 @@
 	</SpriteParticleEmitterComponent>
 
 	<SpriteParticleEmitterComponent
+		_tags="enabled_in_world"
 		sprite_file="data/particles/shine_08.xml"
 		lifetime="0.2"
 		randomize_lifetime.min="0.1"
@@ -123,6 +131,7 @@
 	</SpriteParticleEmitterComponent>
 
 	<SpriteParticleEmitterComponent
+		_tags="enabled_in_world"
 		sprite_file="data/particles/shine_06.xml"
 		lifetime="0.56"
 		emission_interval_min_frames="100"
diff --git a/entities/items/pickup/goldnugget_10000.xml b/entities/items/pickup/goldnugget_10000.xml
index b709015..0747d49 100644
--- a/entities/items/pickup/goldnugget_10000.xml
+++ b/entities/items/pickup/goldnugget_10000.xml
@@ -2,6 +2,7 @@
 
   <!-- physical presence -->
 	<UIInfoComponent
+		_tags="enabled_in_world"
 		name="$item_goldnugget">
 	</UIInfoComponent>
 
@@ -19,7 +20,8 @@
   </PhysicsBodyComponent>
   
   <!-- Thank you Derek! -->
-  <PhysicsImageShapeComponent 
+  <PhysicsImageShapeComponent
+	_tags="enabled_in_world"
     body_id="1"
     centered="1"
     image_file="data/items_gfx/easter/golden_idol.png"
@@ -27,6 +29,7 @@
   </PhysicsImageShapeComponent>
 
   <VariableStorageComponent
+	_tags="enabled_in_world"
     name="gold_value"
     value_int="10000" >
   </VariableStorageComponent>
@@ -56,14 +59,17 @@
   </HitboxComponent>
 
   <LifetimeComponent
+	_tags="enabled_in_world"
     lifetime="900" >
   </LifetimeComponent>
   
-	<LuaComponent 
+	<LuaComponent
+		_tags="enabled_in_world"
 		script_item_picked_up="data/scripts/items/gold_pickup.lua" >
 	</LuaComponent>
 	
-	<LuaComponent 
+	<LuaComponent
+		_tags="enabled_in_world"
 		script_source_file="data/scripts/perks/gold_explosion.lua" 
 		execute_on_added="1"
 		remove_after_executed="1"
@@ -72,6 +78,7 @@
 
       <!-- particle glitter -->
   <SpriteParticleEmitterComponent
+	_tags="enabled_in_world"
     sprite_file="data/particles/shine_07.xml"
     lifetime="0.3"
     emission_interval_min_frames="20"
@@ -97,6 +104,7 @@
   </SpriteParticleEmitterComponent>
 
   <SpriteParticleEmitterComponent
+	_tags="enabled_in_world"
     sprite_file="data/particles/shine_08.xml"
     lifetime="0.2"
     randomize_lifetime.min="0.1"
@@ -124,6 +132,7 @@
   </SpriteParticleEmitterComponent>
 
   <SpriteParticleEmitterComponent
+	_tags="enabled_in_world"
     sprite_file="data/particles/shine_06.xml"
     lifetime="0.56"
     emission_interval_min_frames="100"
diff --git a/entities/items/pickup/goldnugget_200.xml b/entities/items/pickup/goldnugget_200.xml
index 092d134..9704fd5 100644
--- a/entities/items/pickup/goldnugget_200.xml
+++ b/entities/items/pickup/goldnugget_200.xml
@@ -2,10 +2,11 @@
 
 	<!-- physical presence -->
 	<UIInfoComponent
+		_tags="enabled_in_world"
 		name="$item_goldnugget">
 	</UIInfoComponent>
 
-	<PhysicsBodyComponent 
+	<PhysicsBodyComponent
 		_tags="enabled_in_world"
 		uid="1" 
 		allow_sleep="1" 
@@ -18,7 +19,8 @@
 		on_death_leave_physics_body="1" >
 	</PhysicsBodyComponent>
 	
-	<PhysicsImageShapeComponent 
+	<PhysicsImageShapeComponent
+		_tags="enabled_in_world"
 		body_id="1"
 		centered="1"
 		image_file="data/items_gfx/goldnugget_12px.png"
@@ -26,6 +28,7 @@
 	</PhysicsImageShapeComponent>
 
 	<VariableStorageComponent
+		_tags="enabled_in_world"
 		name="gold_value"
 		value_int="200" >
 	</VariableStorageComponent>
@@ -55,14 +58,17 @@
 	</HitboxComponent>
 
 	<LifetimeComponent
+		_tags="enabled_in_world"
 		lifetime="900" >
 	</LifetimeComponent>
 	
-	<LuaComponent 
+	<LuaComponent
+		_tags="enabled_in_world"
 		script_item_picked_up="data/scripts/items/gold_pickup.lua" >
 	</LuaComponent>
 	
-	<LuaComponent 
+	<LuaComponent
+		_tags="enabled_in_world"
 		script_source_file="data/scripts/perks/gold_explosion.lua" 
 		execute_on_added="1"
 		remove_after_executed="1"
@@ -71,6 +77,7 @@
 
 	<!-- particle glitter -->
 	<SpriteParticleEmitterComponent
+		_tags="enabled_in_world"
 		sprite_file="data/particles/shine_07.xml"
 		lifetime="0.3"
 		emission_interval_min_frames="50"
@@ -96,6 +103,7 @@
 	</SpriteParticleEmitterComponent>
 
 	<SpriteParticleEmitterComponent
+		_tags="enabled_in_world"
 		sprite_file="data/particles/shine_08.xml"
 		lifetime="0.2"
 		randomize_lifetime.min="0.1"
diff --git a/entities/items/pickup/goldnugget_50.xml b/entities/items/pickup/goldnugget_50.xml
index 9b4cb4c..3d76d99 100644
--- a/entities/items/pickup/goldnugget_50.xml
+++ b/entities/items/pickup/goldnugget_50.xml
@@ -2,10 +2,11 @@
 
 	<!-- physical presence -->
 	<UIInfoComponent
+		_tags="enabled_in_world"
 		name="$item_goldnugget">
 	</UIInfoComponent>
 
-	<PhysicsBodyComponent 
+	<PhysicsBodyComponent
 		_tags="enabled_in_world"
 		uid="1" 
 		allow_sleep="1" 
@@ -18,7 +19,8 @@
 		on_death_leave_physics_body="1" >
 	</PhysicsBodyComponent>
 	
-	<PhysicsImageShapeComponent 
+	<PhysicsImageShapeComponent
+		_tags="enabled_in_world"
 		body_id="1"
 		centered="1"
 		image_file="data/items_gfx/goldnugget_9px.png"
@@ -26,6 +28,7 @@
 	</PhysicsImageShapeComponent>
 
 	<VariableStorageComponent
+		_tags="enabled_in_world"
 		name="gold_value"
 		value_int="50" >
 	</VariableStorageComponent>
@@ -55,14 +58,17 @@
 	</HitboxComponent>
 
 	<LifetimeComponent
+		_tags="enabled_in_world"
 		lifetime="900" >
 	</LifetimeComponent>
 	
-	<LuaComponent 
+	<LuaComponent
+		_tags="enabled_in_world"
 		script_item_picked_up="data/scripts/items/gold_pickup.lua" >
 	</LuaComponent>
 	
-	<LuaComponent 
+	<LuaComponent
+		_tags="enabled_in_world"
 		script_source_file="data/scripts/perks/gold_explosion.lua" 
 		execute_on_added="1"
 		remove_after_executed="1"
@@ -71,6 +77,7 @@
 
 	<!-- particle glitter -->
 	<SpriteParticleEmitterComponent
+		_tags="enabled_in_world"
 		sprite_file="data/particles/shine_07.xml"
 		lifetime="0.3"
 		emission_interval_min_frames="100"
@@ -96,6 +103,7 @@
 	</SpriteParticleEmitterComponent>
 
 	<SpriteParticleEmitterComponent
+		_tags="enabled_in_world"
 		sprite_file="data/particles/shine_08.xml"
 		lifetime="0.2"
 		randomize_lifetime.min="0.1"
diff --git a/entities/misc/effect_trip_03.xml b/entities/misc/effect_trip_03.xml
index 1ff4dc5..043ed3e 100644
--- a/entities/misc/effect_trip_03.xml
+++ b/entities/misc/effect_trip_03.xml
@@ -1,4 +1,4 @@
-<Entity name="effect_tripping_balls">
+<Entity name="effect_tripping_balls" tags="tripping_extreme">
 
 	<InheritTransformComponent>
     </InheritTransformComponent>
diff --git a/entities/player_base.xml b/entities/player_base.xml
index 2e60357..ad5ff78 100644
--- a/entities/player_base.xml
+++ b/entities/player_base.xml
@@ -428,6 +428,18 @@
 		z_index="0.59"
 		_enabled="0"
 	></SpriteComponent>
+	
+	<SpriteComponent 
+		_tags="character,player_hat"
+		alpha="1" 
+		image_file="data/enemies_gfx/player_hat.xml" 
+		next_rect_animation="" 
+		offset_x="6" 
+		offset_y="14" 
+		rect_animation="walk" 
+		z_index="0.59"
+		_enabled="0"
+	></SpriteComponent>
 
 	<LuaComponent
 		script_source_file="data/scripts/magic/amulet.lua"
diff --git a/entities/projectiles/deck/iceball.xml b/entities/projectiles/deck/iceball.xml
index f9adafe..2807b88 100644
--- a/entities/projectiles/deck/iceball.xml
+++ b/entities/projectiles/deck/iceball.xml
@@ -195,13 +195,128 @@
   </LightComponent>
 
   <MagicConvertMaterialComponent
-        from_material=""
-        to_material=""
-        steps_per_frame="5"
-		extinguish_fire="1"
+        from_material="fire"
+        to_material="air"
+        steps_per_frame="20"
         loop="1"
-        is_circle="1"
-        radius="15" >
+		is_circle="1"
+        radius="20" >
+    </MagicConvertMaterialComponent>
+	
+	<MagicConvertMaterialComponent
+        from_material="lava"
+        to_material="rock_static"
+        steps_per_frame="20"
+        loop="1"
+		is_circle="1"
+        radius="20" >
+    </MagicConvertMaterialComponent>
+	
+    <MagicConvertMaterialComponent
+        from_material="water"
+        to_material="ice_static"
+        steps_per_frame="20"
+        loop="1"
+		is_circle="1"
+        radius="20" >
+    </MagicConvertMaterialComponent>
+
+    <MagicConvertMaterialComponent
+        from_material="water_ice"
+        to_material="ice_static"
+        steps_per_frame="20"
+        loop="1"
+		is_circle="1"
+        radius="20" >
+    </MagicConvertMaterialComponent>
+
+    <MagicConvertMaterialComponent
+        from_material="water_salt"
+        to_material="ice_static"
+        steps_per_frame="20"
+        loop="1"
+		is_circle="1"
+        radius="20" >
+    </MagicConvertMaterialComponent>
+
+    <MagicConvertMaterialComponent
+        from_material="water_static"
+        to_material="ice_static"
+        steps_per_frame="20"
+        loop="1"
+		is_circle="1"
+        radius="20" >
+    </MagicConvertMaterialComponent>
+
+    <MagicConvertMaterialComponent
+        from_material="water_swamp"
+        to_material="ice_static"
+        steps_per_frame="20"
+        loop="1"
+		is_circle="1"
+        radius="20" >
+    </MagicConvertMaterialComponent>
+	
+	<MagicConvertMaterialComponent
+        from_material="radioactive_liquid"
+        to_material="ice_radioactive_static"
+        steps_per_frame="20"
+        loop="1"
+		is_circle="1"
+        radius="20" >
+    </MagicConvertMaterialComponent>
+	
+	<MagicConvertMaterialComponent
+        from_material="acid"
+        to_material="ice_acid_static"
+        steps_per_frame="20"
+        loop="1"
+		is_circle="1"
+        radius="20" >
+    </MagicConvertMaterialComponent>
+	
+	<MagicConvertMaterialComponent
+        from_material="blood_cold"
+        to_material="ice_cold_static"
+        steps_per_frame="20"
+        loop="1"
+		is_circle="1"
+        radius="20" >
+    </MagicConvertMaterialComponent>
+	
+	<MagicConvertMaterialComponent
+        from_material="blood"
+        to_material="ice_blood_static"
+        steps_per_frame="20"
+        loop="1"
+		is_circle="1"
+        radius="20" >
+    </MagicConvertMaterialComponent>
+	
+	<MagicConvertMaterialComponent
+        from_material="poison"
+        to_material="ice_poison_static"
+        steps_per_frame="20"
+        loop="1"
+		is_circle="1"
+        radius="20" >
+    </MagicConvertMaterialComponent>
+	
+	<MagicConvertMaterialComponent
+        from_material="slime"
+        to_material="ice_slime_static"
+        steps_per_frame="20"
+        loop="1"
+		is_circle="1"
+        radius="20" >
+    </MagicConvertMaterialComponent>
+    
+    <MagicConvertMaterialComponent
+      kill_when_finished="0"
+      extinguish_fire="1"
+      is_circle="1"
+      loop="1"
+      radius="30" >
     </MagicConvertMaterialComponent>
 
   <AudioComponent
diff --git a/entities/projectiles/deck/pebble_player_physics.xml b/entities/projectiles/deck/pebble_player_physics.xml
index cc9d6a1..33f3aff 100644
--- a/entities/projectiles/deck/pebble_player_physics.xml
+++ b/entities/projectiles/deck/pebble_player_physics.xml
@@ -64,6 +64,7 @@
 			blood_spray_material="blood_cold"
 			blood_sprite_directional="data/particles/bloodsplatters/bloodsplatter_directional_blue_$[1-3].xml"
 			blood_sprite_large="data/particles/bloodsplatters/bloodsplatter_blue_$[1-3].xml"
+			healing_particle_effect_entity="data/entities/particles/heal_effect.xml"
 			>
 			<damage_multipliers
 				melee="0.0"
diff --git a/entities/projectiles/deck/powerdigger.xml b/entities/projectiles/deck/powerdigger.xml
index 09a049e..ade36e4 100644
--- a/entities/projectiles/deck/powerdigger.xml
+++ b/entities/projectiles/deck/powerdigger.xml
@@ -69,8 +69,6 @@
       is_digger="1"
       audio_enabled="0" >
     </config_explosion>
-    <damage_by_type drill="0.01" >
-    </damage_by_type>
   </ProjectileComponent>
   
   <SpriteParticleEmitterComponent
diff --git a/genome_relations.csv b/genome_relations.csv
index ff11f41..13aeb3c 100644
--- a/genome_relations.csv
+++ b/genome_relations.csv
@@ -1,5 +1,5 @@
 HERD,player,-1,slimes,ant,robot,fly,boss_dragon,crawler,helpless,eel,fire,fungus,ghoul,giant,ice,spider,orcs,rat,electricity,wolf,worm,zombie,nest,mage,flower,ghost,boss_limbs,healer,apparition,bat,mage_swapper,curse,trap,ghost_boss
-      player,100,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0
+      player,100,0,0,0,0,0,0,0,100,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0
 -1,0,100,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,100,0,100,0,0,0,0
       slimes,0,0,100,80,95,90,0,0,0,90,90,90,90,90,90,95,95,30,90,90,90,90,100,90,90,90,0,100,50,100,90,100,100,100
          ant,0,0,80,100,40,90,0,0,0,0,0,100,0,0,0,95,40,50,0,0,0,90,100,90,90,90,0,100,50,100,90,100,100,100
diff --git a/items_gfx/wands/custom/skull_01.png b/items_gfx/wands/custom/skull_01.png
index 68f099b..45cf132 100644
Binary files a/items_gfx/wands/custom/skull_01.png and b/items_gfx/wands/custom/skull_01.png differ
diff --git a/materials.xml b/materials.xml
index 314d445..3680fe6 100644
--- a/materials.xml
+++ b/materials.xml
@@ -2976,7 +2976,6 @@
   	_parent="steel_static"
   	_inherit_reactions="1"
   	name="steelmoss_static"
-  	<!-- steel_rusted -->
 	ui_name="$mat_steelrusted"	
 	wang_color="ff787A55" 
 	wang_noise_percent="0.0"
@@ -8040,7 +8039,6 @@
 	solid_friction="1.0"
 	fire_hp="50"
 	on_fire="0"
-	temperature_of_fire="95"
 	autoignition_temperature="10"
 	electrical_conductivity="0"
 	requires_oxygen="1"  
@@ -9640,7 +9638,7 @@
 	name="rat_powder"
 	ui_name="$mat_rat_powder"
   	tags="[sand_other]"
-	burnable="1"
+	burnable="0"
 	density="7"
 	durability="3"
 	cell_type="liquid"
@@ -9648,7 +9646,7 @@
 	generates_smoke="0"
 	liquid_gravity="2"
 	liquid_sand="1"
-	on_fire="1"
+	on_fire="0"
 	requires_oxygen="0"
 	temperature_of_fire="10"
 	autoignition_temperature="0"
@@ -9662,25 +9660,6 @@
 	show_in_creative_mode="0"
 	lifetime="4.0"
 	>
-	<ExplosionConfig 
-		damage="0"
-		cell_explosion_power="2"
-		cell_explosion_damage_required="1"
-		cell_explosion_radius_min="2"
-		explosion_sprite=""
-		load_this_entity="data/entities/misc/rat_powder.xml"
-		ray_energy="0"
-		audio_enabled="0"
-		create_cell_probability="0"
-		sparks_enabled="0"
-		light_enabled="0"
-		hole_enabled="1"
-		crack_count="0"
-		stains_enabled="0"
-		damage_mortals="0"
-		particle_effect="0"
-		>
-	</ExplosionConfig>
     <Graphics
 	  texture_file="data/materials_gfx/meat_rotten.png"
 	  color="ffb89e57" >
@@ -9700,7 +9679,7 @@
 	name="fungus_powder"
 	ui_name="$mat_fungisoil"
   	tags="[sand_other]"
-	burnable="1"
+	burnable="0"
 	density="7"
 	durability="3"
 	cell_type="liquid"
@@ -9708,7 +9687,7 @@
 	generates_smoke="0"
 	liquid_gravity="2"
 	liquid_sand="1"
-	on_fire="1"
+	on_fire="0"
 	requires_oxygen="0"
 	temperature_of_fire="10"
 	autoignition_temperature="0"
@@ -9722,25 +9701,6 @@
 	show_in_creative_mode="0"
 	lifetime="4.0"
 	>
-	<ExplosionConfig 
-		damage="0"
-		cell_explosion_power="2"
-		cell_explosion_damage_required="1"
-		cell_explosion_radius_min="2"
-		explosion_sprite=""
-		load_this_entity="data/entities/misc/fungus_powder.xml"
-		ray_energy="0"
-		audio_enabled="0"
-		create_cell_probability="0"
-		sparks_enabled="0"
-		light_enabled="0"
-		hole_enabled="1"
-		crack_count="0"
-		stains_enabled="0"
-		damage_mortals="0"
-		particle_effect="0"
-		>
-	</ExplosionConfig>
     <Graphics
 	  texture_file="data/materials_gfx/meat_rotten.png"
 	  color="ffb89e57" >
@@ -11434,6 +11394,7 @@
 	density="8"
 	cell_type="solid"
 	wang_color="ffab5e4f"
+	durability="11"
 	generates_smoke="0"
 	on_fire="0"
 	requires_oxygen="1"
@@ -11441,12 +11402,13 @@
 	autoignition_temperature="85"
 	fire_hp="600"
 	solid_friction="0.9"
-	hp="500"
+	hp="10000"
 	audio_physics_material_wall="gravel"
 	audio_physics_material_solid="wood"
 	show_in_creative_mode="1"
 	>
-	<ExplosionConfig 
+	<ExplosionConfig
+		damage="5"
       	camera_shake="10" 
 		cell_explosion_power="40"
 		cell_explosion_damage_required="30"
@@ -13362,15 +13324,17 @@
 	color="80c1dba5" >
     </Graphics>
 	<ParticleEffect
-		vel.y="17.14"
-		vel_random.min_y="-100"
-		vel_random.max_y="25.71"
+		vel.y="2.14"
+		vel_random.min_y="-55"
+		vel_random.max_y="25"
 		lifetime.min="0"
-		gravity.y="-8.57"
+		gravity.y="0"
 		render_on_grid="1"
+		airflow_force="3"
+		airflow_scale="0.1"
 		draw_as_long="1"
-		friction="-3.429"
-		probability="0.0518"
+		friction="0.04"
+		probability="0.0118"
 	>
 	</ParticleEffect>
   </CellData>
@@ -14880,6 +14844,21 @@
 		output_cell1="metal_sand_molten" output_cell2="[lava]"
 		>
 	</Reaction>
-
+	
+	<!-- Special powders -->
+	
+	<Reaction probability="100"
+		input_cell1="rat_powder" input_cell2="air"
+		output_cell1="air" output_cell2="air"
+		entity="data/entities/misc/rat_powder.xml"
+		>
+	</Reaction>
+	
+	<Reaction probability="100"
+		input_cell1="fungus_powder" input_cell2="air"
+		output_cell1="air" output_cell2="air"
+		entity="data/entities/misc/fungus_powder.xml"
+		>
+	</Reaction>
 
 </Materials>
diff --git a/scripts/animals/fungus_powder.lua b/scripts/animals/fungus_powder.lua
index d3b8de0..1b6091a 100644
--- a/scripts/animals/fungus_powder.lua
+++ b/scripts/animals/fungus_powder.lua
@@ -7,7 +7,7 @@ SetRandomSeed( x, y )
 local rats = EntityGetWithTag( "perk_fungus_tiny" )
 
 if ( #rats < 20 ) then
-	if ( Random( 1, 15 ) == 5 ) then
+	if ( Random( 1, 20 ) == 5 ) then
 		local eid = EntityLoad( "data/entities/misc/perks/fungus.xml", x, y )
 		EntityRemoveTag( eid, "enemy" )
 	end
diff --git a/scripts/animals/rat_powder.lua b/scripts/animals/rat_powder.lua
index 90b56de..309c3ff 100644
--- a/scripts/animals/rat_powder.lua
+++ b/scripts/animals/rat_powder.lua
@@ -7,7 +7,7 @@ SetRandomSeed( x, y )
 local rats = EntityGetWithTag( "plague_rat" )
 
 if ( #rats < 20 ) then
-	if ( Random( 1, 15 ) == 5 ) then
+	if ( Random( 1, 20 ) == 5 ) then
 		EntityLoad( "data/entities/misc/perks/plague_rats_rat.xml", x, y )
 	end
 end
diff --git a/scripts/biomes/gourd_room.lua b/scripts/biomes/gourd_room.lua
index c466b68..cb9ee3e 100644
--- a/scripts/biomes/gourd_room.lua
+++ b/scripts/biomes/gourd_room.lua
@@ -5,6 +5,7 @@ dofile_once("data/scripts/lib/utilities.lua")
 
 RegisterSpawnFunction( 0xffffeedd, "init" )
 RegisterSpawnFunction( 0xff31d0b0, "spawn_fruit" )
+RegisterSpawnFunction( 0xff9dd0b0, "spawn_book" )
 
 function spawn_small_enemies( x, y ) end
 function spawn_big_enemies( x, y ) end
@@ -24,7 +25,7 @@ function spawn_potions( x, y ) end
 function spawn_wands( x, y ) end
 
 function init( x, y, w, h )
-	LoadPixelScene( "data/biome_impl/gourd_room.png", "", x, y, "", true )
+	--LoadPixelScene( "data/biome_impl/gourd_room.png", "", x, y, "", true )
 end
 
 function spawn_orb(x, y)
@@ -39,6 +40,12 @@ function spawn_fruit( x, y )
 	EntityLoad( "data/entities/animals/shotgunner.xml", x + 24, y - 24 )
 end
 
+function spawn_book( x, y )
+	EntityLoad( "data/entities/items/books/book_music_c.xml", x, y )
+	EntityLoad( "data/entities/props/physics_skull_01.xml", x + 8, y )
+	EntityLoad( "data/entities/props/physics_bone_02.xml", x + 12, y - 16 )
+end
+
 g_lamp =
 {
 	total_prob = 0,
diff --git a/scripts/biomes/mountain_tree.lua b/scripts/biomes/mountain_tree.lua
index 47f851d..4cbd5a7 100644
--- a/scripts/biomes/mountain_tree.lua
+++ b/scripts/biomes/mountain_tree.lua
@@ -293,7 +293,7 @@ function spawn_pillars( x, y )
 	SetRandomSeed( x, y )
 	local flags = 
 	{
-		{ { "misc_chest_rain", "crain" }, { "misc_worm_rain", "wrain" }, { "misc_greed_rain", "grain" }, { "misc_altar_tablet", "train" }, { "misc_monk_bots", "mbots" }, { "secret_tower", "secrett" }, { "player_status_ghostly", "pghost" }, { "player_status_ratty", "prat" } },
+		{ { "misc_chest_rain", "crain" }, { "misc_worm_rain", "wrain" }, { "misc_greed_rain", "grain" }, { "misc_altar_tablet", "train" }, { "misc_monk_bots", "mbots" }, { "secret_tower", "secrett" }, { "player_status_ghostly", "pghost" }, { "player_status_ratty", "prat" }, { "player_status_funky", "pfungi" } },
 		{ { "essence_fire", "essencef" }, { "essence_water", "essencew" }, { "essence_laser", "essencee" }, { "essence_air", "essencea" }, { "essence_alcohol", "essenceal" }, { "secret_moon", "moon" }, { "secret_moon2", "moona" }, { "special_mood", "moong" }, { "secret_dmoon", "dmoon" }, { "dead_mood", "dmoong" } },
 		{ { "progress_ending0", "end0" }, { "progress_ending1_toxic", "endt" }, { "progress_ending1_gold", "endb" }, { "progress_ending2", "endg" }, { "progress_newgameplusplus3", "endp" }, { "progress_nightmare", "endn" } },
 		{ { "miniboss_dragon", "minid" }, { "miniboss_limbs", "minil" }, { "miniboss_ghost", "minigh" }, { "miniboss_pit", "minip" }, { "miniboss_alchemist", "minia" }, { "miniboss_wizard", "meme" }, { "miniboss_gate_monsters", "minigm" }, { "boss_centipede", "boss" } },
diff --git a/scripts/biomes/pyramid.lua b/scripts/biomes/pyramid.lua
index 16e5fc7..3e47e10 100644
--- a/scripts/biomes/pyramid.lua
+++ b/scripts/biomes/pyramid.lua
@@ -668,4 +668,5 @@ end
 
 function spawn_boss_limbs_trigger( x, y )
 	EntityLoad("data/entities/animals/boss_limbs/boss_limbs_trigger.xml", x, y )
+	EntityLoad("data/entities/items/books/book_music_b.xml", x, y )
 end
\ No newline at end of file
diff --git a/scripts/biomes/vault.lua b/scripts/biomes/vault.lua
index 01080e9..e6be826 100644
--- a/scripts/biomes/vault.lua
+++ b/scripts/biomes/vault.lua
@@ -551,7 +551,7 @@ g_pixel_scene_02 =
 		is_unique		= 0,
 	},
 	{
-		prob   			= 0.5,
+		prob   			= 0.3,
 		material_file 	= "data/biome_impl/vault/lab_puzzle.png",
 		visual_file		= "data/biome_impl/vault/lab_puzzle_visual.png",
 		background_file	= "data/biome_impl/vault/lab_puzzle_background.png",
diff --git a/scripts/buildings/vault_lab_puzzle_check.lua b/scripts/buildings/vault_lab_puzzle_check.lua
index 688a81f..7da2601 100644
--- a/scripts/buildings/vault_lab_puzzle_check.lua
+++ b/scripts/buildings/vault_lab_puzzle_check.lua
@@ -7,12 +7,17 @@ function material_area_checker_success( pos_x, pos_y )
 	local spawn_x = x + 70
 	local spawn_y = y + 10
 	
-	EntityLoad( "data/entities/items/pickup/chest_random.xml", spawn_x, spawn_y)
+	-- reward
 	EntityLoad("data/entities/particles/image_emitters/magical_symbol.xml", spawn_x, spawn_y)
 	GamePlaySound( "data/audio/Desktop/projectiles.snd", "player_projectiles/crumbling_earth/create", spawn_x, spawn_y)
-	
-	print("puzzle done")
-	
+	if ProceduralRandomf(x,y) > 0.3 then
+		--EntityLoad( "data/entities/items/pickup/chest_random.xml", spawn_x, spawn_y)
+		EntityLoad( "data/entities/items/wand_arpaluu.xml", spawn_x, spawn_y)
+	else
+		EntityLoad( "data/entities/items/wand_varpuluuta.xml", spawn_x, spawn_y)
+	end
+
+	-- cleanup
 	for _,v in ipairs(EntityGetInRadiusWithTag( x, y, 30,"vault_lab_puzzle")) do
 		EntityKill(v)
 	end
diff --git a/scripts/gun/gun_actions.lua b/scripts/gun/gun_actions.lua
index 3ef1f90..1af6dd2 100644
--- a/scripts/gun/gun_actions.lua
+++ b/scripts/gun/gun_actions.lua
@@ -773,6 +773,26 @@ actions =
 			shot_effects.recoil_knockback = 30.0
 		end,
 	},
+	{
+		id          = "POLLEN",
+		name 		= "$action_pollen",
+		description = "$actiondesc_pollen",
+		sprite 		= "data/ui_gfx/gun_actions/pollen.png",
+		sprite_unidentified = "data/ui_gfx/gun_actions/arrow_unidentified.png",
+		related_projectiles	= {"data/entities/projectiles/deck/pollen.xml"},
+		type 		= ACTION_TYPE_PROJECTILE,
+		spawn_level                       = "0,1,3,4", -- ARROW
+		spawn_probability                 = "0.6,1,1,0.8", -- ARROW
+		price = 110,
+		mana = 10,
+		--max_uses = 40,
+		action 		= function()
+			add_projectile("data/entities/projectiles/deck/pollen.xml")
+			-- damage = 0.3
+			c.fire_rate_wait = c.fire_rate_wait + 2
+			c.spread_degrees = c.spread_degrees + 20
+		end,
+	},
 	{
 		id          = "LANCE",
 		name 		= "$action_lance",
@@ -2114,6 +2134,42 @@ actions =
 			c.fire_rate_wait = c.fire_rate_wait - 12
 		end,
 	},
+	{
+		id          = "TNTBOX",
+		name 		= "$action_tntbox",
+		description = "$actiondesc_tntbox",
+		sprite 		= "data/ui_gfx/gun_actions/tntbox.png",
+		sprite_unidentified = "data/ui_gfx/gun_actions/bomb_unidentified.png",
+		related_projectiles	= {"data/entities/projectiles/deck/tntbox.xml"},
+		type 		= ACTION_TYPE_PROJECTILE,
+		spawn_level                       = "1,2,3,4,5", -- SUMMON_ROCK
+		spawn_probability                 = "0.8,0.8,0.8,0.8,0.8", -- SUMMON_ROCK
+		price = 150,
+		mana = 40, 
+		max_uses    = 15, 
+		action 		= function()
+			add_projectile("data/entities/projectiles/deck/tntbox.xml")
+			c.fire_rate_wait = c.fire_rate_wait + 30
+		end,
+	},
+	{
+		id          = "TNTBOX_BIG",
+		name 		= "$action_tntbox_big",
+		description = "$actiondesc_tntbox_big",
+		sprite 		= "data/ui_gfx/gun_actions/tntbox_big.png",
+		sprite_unidentified = "data/ui_gfx/gun_actions/bomb_unidentified.png",
+		related_projectiles	= {"data/entities/projectiles/deck/tntbox_big.xml"},
+		type 		= ACTION_TYPE_PROJECTILE,
+		spawn_level                       = "1,2,3,4,5", -- SUMMON_ROCK
+		spawn_probability                 = "0.8,0.8,0.8,0.8,0.8", -- SUMMON_ROCK
+		price = 170,
+		mana = 40, 
+		max_uses    = 15, 
+		action 		= function()
+			add_projectile("data/entities/projectiles/deck/tntbox_big.xml")
+			c.fire_rate_wait = c.fire_rate_wait + 30
+		end,
+	},
 	{
 		id          = "SWARM_FLY",
 		name 		= "$action_swarm_fly",
@@ -4670,7 +4726,7 @@ actions =
 		related_extra_entities = { "data/entities/misc/homing_cursor.xml", "data/entities/particles/tinyspark_white.xml" },
 		type 		= ACTION_TYPE_MODIFIER,
 		spawn_level                       = "2,3,4,5,6", -- HOMING_ROTATE
-		spawn_probability                 = "0.4,0.4,0.4,0.4,0.4", -- HOMING_ROTATE
+		spawn_probability                 = "0.7,0.7,0.4,0.4,1.0", -- HOMING_ROTATE
 		price = 175,
 		mana = 30,
 		--max_uses = 100,
@@ -6771,10 +6827,10 @@ actions =
 		related_extra_entities = { "data/entities/misc/orbit_discs.xml" },
 		spawn_requires_flag = "card_unlocked_dragon",
 		type 		= ACTION_TYPE_MODIFIER,
-		spawn_level                       = "0,1,2,4,5", -- GRAVITY_FIELD_ENEMY
-		spawn_probability                 = "0.5,0.2,0.8,0.4,0.2", -- GRAVITY_FIELD_ENEMY
-		price = 140,
-		mana = 40,
+		spawn_level                       = "1,2,4,5", -- GRAVITY_FIELD_ENEMY
+		spawn_probability                 = "0.2,0.8,0.4,0.2", -- GRAVITY_FIELD_ENEMY
+		price = 200,
+		mana = 70,
 		action 		= function()
 			c.extra_entities = c.extra_entities .. "data/entities/misc/orbit_discs.xml,"
 			draw_actions( 1, true )
diff --git a/scripts/item_spawnlists.lua b/scripts/item_spawnlists.lua
index b17ad02..ac97ca7 100644
--- a/scripts/item_spawnlists.lua
+++ b/scripts/item_spawnlists.lua
@@ -3,19 +3,23 @@ spawnlists =
 	potion_spawnlist =
 	{
 		rnd_min = 1,
-		rnd_max = 92,
+		rnd_max = 91,
 		spawns = 
 		{
-			{
-				value_min = 92,
-				value_max = 92,
-				load_entity = "data/entities/items/pickup/stonestone.xml",
-				offset_y = -2,
-			},
 			{
 				value_min = 90,
 				value_max = 91,
-				load_entity = "data/entities/items/pickup/physics_gold_orb.xml",
+				load_entity_func = 
+					function( data, x, y )
+						local ox = data.offset_x or 0
+						local oy = data.offset_y or 0
+						
+						if GameHasFlagRun( "greed_curse" ) and ( GameHasFlagRun( "greed_curse_gone" ) == false ) then
+							EntityLoad( "data/entities/items/pickup/physics_gold_orb_greed.xml", x + ox, y + oy )
+						else
+							EntityLoad( "data/entities/items/pickup/physics_gold_orb.xml", x + ox, y + oy )
+						end
+					end,
 				offset_y = -2,
 			},
 			{
diff --git a/scripts/items/chest_random.lua b/scripts/items/chest_random.lua
index 0c54d53..bda5ff3 100644
--- a/scripts/items/chest_random.lua
+++ b/scripts/items/chest_random.lua
@@ -189,7 +189,11 @@ function drop_random_reward( x, y, entity_id, rand_x, rand_y, set_rnd_  )
 				
 				opt = "data/entities/items/pickup/runestones/runestone_" .. r_opt .. ".xml"
 			elseif ( opt == "orb" ) then
-				opt = "data/entities/items/pickup/physics_gold_orb.xml"
+				if GameHasFlagRun( "greed_curse" ) and ( GameHasFlagRun( "greed_curse_gone" ) == false ) then
+					opt = "data/entities/items/pickup/physics_gold_orb_greed.xml"
+				else
+					opt = "data/entities/items/pickup/physics_gold_orb.xml"
+				end
 			end
 			
 			table.insert( entities, { opt, x, y - 10 } )
diff --git a/scripts/items/gold_orb.lua b/scripts/items/gold_orb.lua
index beba6a2..8f29f1a 100644
--- a/scripts/items/gold_orb.lua
+++ b/scripts/items/gold_orb.lua
@@ -6,6 +6,8 @@ function drop()
 	
 	local comp = EntityGetFirstComponent( entity_id, "VariableStorageComponent", "kick_count" )
 	
+	SetRandomSeed( GameGetFrameNum(), x + y + entity_id )
+	
 	if ( comp ~= nil ) then
 		local count = ComponentGetValue2( comp, "value_int" )
 		count = count + 1
@@ -28,15 +30,15 @@ function drop()
 			EntityKill( entity_id )
 			return
 		elseif ( outcome == 20 ) then
-			EntityLoad( "data/entities/items/pickup/goldnugget_200.xml", x, y )
+			shoot_projectile( entity_id, "data/entities/items/pickup/goldnugget_200.xml", x, y, Random(-40,40), Random(-40,40) )
 		elseif ( outcome == 15 ) then
-			EntityLoad( "data/entities/items/pickup/goldnugget_50.xml", x + 8, y )
-			EntityLoad( "data/entities/items/pickup/goldnugget_50.xml", x - 8, y )
+			shoot_projectile( entity_id, "data/entities/items/pickup/goldnugget_50.xml", x - 8, y, Random(-40,40), Random(-40,40) )
+			shoot_projectile( entity_id, "data/entities/items/pickup/goldnugget_50.xml", x + 8, y, Random(-40,40), Random(-40,40) )
 		elseif ( outcome < 10 ) then
-			EntityLoad( "data/entities/items/pickup/goldnugget_10.xml", x, y )
+			shoot_projectile( entity_id, "data/entities/items/pickup/goldnugget_10.xml", x, y, Random(-40,40), Random(-40,40) )
 		else
-			EntityLoad( "data/entities/items/pickup/goldnugget_10.xml", x + 8, y )
-			EntityLoad( "data/entities/items/pickup/goldnugget_10.xml", x - 8, y )
+			shoot_projectile( entity_id, "data/entities/items/pickup/goldnugget_10.xml", x - 8, y, Random(-40,40), Random(-40,40) )
+			shoot_projectile( entity_id, "data/entities/items/pickup/goldnugget_10.xml", x + 8, y, Random(-40,40), Random(-40,40) )
 		end
 	end
 end
diff --git a/scripts/items/greed_die_status.lua b/scripts/items/greed_die_status.lua
index 42eef46..e58a573 100644
--- a/scripts/items/greed_die_status.lua
+++ b/scripts/items/greed_die_status.lua
@@ -26,14 +26,7 @@ function bullet_circle( which, count, speed, animal_, gold_ )
 		
 		local bid
 		
-		if ( gold == false ) then
-			bid = shoot_projectile( entity_id, target, pos_x + math.cos( theta ) * 12, pos_y - math.sin( theta ) * 12, vel_x, vel_y )
-		else
-			bid = EntityLoad( target, pos_x + math.cos( theta ) * 12, pos_y - math.sin( theta ) * 12 )
-			edit_component( bid, "VelocityComponent", function(comp,vars)
-				ComponentSetValueVector2( comp, "mVelocity", vel_x, vel_y )
-			end)
-		end
+		bid = shoot_projectile( entity_id, target, pos_x + math.cos( theta ) * 12, pos_y - math.sin( theta ) * 12, vel_x, vel_y )
 		
 		if ( bid ~= nil ) and animal then
 			EntityAddComponent( bid, "VariableStorageComponent", 
diff --git a/scripts/magic/fungal_shift.lua b/scripts/magic/fungal_shift.lua
index c3be6d0..ee73498 100644
--- a/scripts/magic/fungal_shift.lua
+++ b/scripts/magic/fungal_shift.lua
@@ -8,11 +8,16 @@ materials_from =
 	{ probability = 1.0, materials = { "oil", "swamp", "peat" }, name_material = "oil" },
 	{ probability = 1.0, materials = { "blood" } },	-- NOTE(Olli): I'm not sure if it's a good idea to convert blood, because that often just feels buggy. but let's see.
 	{ probability = 1.0, materials = { "blood_fungi", "fungi", "fungisoil" }, name_material = "fungi" },
-	{ probability = 1.0, materials = { "blood_cold" } },
+	{ probability = 1.0, materials = { "blood_cold", "blood_worm" } },
 	{ probability = 1.0, materials = { "acid" } },
-	{ probability = 1.0, materials = { "magic_liquid_polymorph", "magic_liquid_unstable_polymorph" }, name_material = "magic_liquid_polymorph" },
-	{ probability = 1.0, materials = { "magic_liquid_teleportation", "magic_liquid_unstable_teleportation" }, name_material = "magic_liquid_teleportation" },
-	{ probability = 1.0, materials = { "magic_liquid_berserk", "magic_liquid_charm", "magic_liquid_invisibility" } },
+	{ probability = 0.4, materials = { "magic_liquid_polymorph", "magic_liquid_unstable_polymorph" }, name_material = "magic_liquid_polymorph" },
+	{ probability = 0.4, materials = { "magic_liquid_teleportation", "magic_liquid_unstable_teleportation" }, name_material = "magic_liquid_teleportation" },
+	{ probability = 0.4, materials = { "magic_liquid_berserk", "magic_liquid_charm", "magic_liquid_invisibility" } },
+	{ probability = 0.6, materials = { "diamond" } },
+	{ probability = 0.6, materials = { "silver", "brass", "copper" } },
+	{ probability = 0.05, materials = { "sand" } },
+	{ probability = 0.05, materials = { "snow_sticky" } },
+	{ probability = 0.001, materials = { "gold", "gold_box2d" }, name_material = "gold" },
 }
 
 materials_to = 
@@ -32,11 +37,20 @@ materials_to =
 	{ probability = 1.00, material = "vomit" },
 	{ probability = 1.00, material = "pea_soup" },
 	{ probability = 1.00, material = "fungi" },
+	{ probability = 0.80, material = "sand" },
+	{ probability = 0.80, material = "diamond" },
+	{ probability = 0.80, material = "silver" },
+	{ probability = 0.80, material = "steam" },
+	{ probability = 0.50, material = "rock_static" },
+	{ probability = 0.50, material = "material_darkness" },
+	{ probability = 0.50, material = "material_confusion" },
+	{ probability = 0.20, material = "rock_static_radioactive" },
 	{ probability = 0.02, material = "magic_liquid_polymorph" },
 	{ probability = 0.02, material = "magic_liquid_random_polymorph" },
 	{ probability = 0.15, material = "magic_liquid_teleportation" },
 	{ probability = 0.01, material = "urine" },
 	{ probability = 0.01, material = "poo" },
+	{ probability = 0.01, material = "cheese_static" },
 }
 
 log_messages = 
@@ -81,10 +95,6 @@ end
 -- TODO: pick one of the materials from cape
 -- TODO: pick one of the materials from a potion?
 function fungal_shift( entity, x, y, debug_no_limits )
-end
-
-function fungal_shift( entity, x, y, debug_no_limits )
-	--[[
 	local parent = EntityGetParent( entity )
 	if parent ~= 0 then
 		entity = parent
@@ -122,7 +132,7 @@ function fungal_shift( entity, x, y, debug_no_limits )
 		local to_material = CellFactory_GetType( to.material )
 		from_material_name = string.upper( GameTextGetTranslatedOrNot( CellFactory_GetUIName( from_material ) ) )
 		if from.name_material then
-			from_material_name = string.upper( GameTextGetTranslatedOrNot( CellFactory_GetUIName( from.name_material ) ) )
+			from_material_name = string.upper( GameTextGetTranslatedOrNot( CellFactory_GetUIName( CellFactory_GetType( from.name_material ) ) ) )
 		end
 
 		-- if a potion is equipped, use main material from potion as one of the materials
@@ -151,7 +161,7 @@ function fungal_shift( entity, x, y, debug_no_limits )
 	if converted_any then
 		-- audio
 		GameTriggerMusicFadeOutAndDequeueAll( 5.0 )
-		GameTriggerMusicEvent( "music/oneshot/tripping_balls", false, x, y )
+		GameTriggerMusicEvent( "music/oneshot/tripping_balls_01", false, x, y )
 
 		-- particle fx
 		local eye = EntityLoad( "data/entities/particles/treble_eye.xml", x,y-10 )
@@ -191,5 +201,4 @@ function fungal_shift( entity, x, y, debug_no_limits )
 			EntityAddChild( entity, icon_entity )
 		end
 	end
-	]]--
 end
diff --git a/scripts/perks/angry_levitation_death.lua b/scripts/perks/angry_levitation_death.lua
index 3898f5b..2833c7c 100644
--- a/scripts/perks/angry_levitation_death.lua
+++ b/scripts/perks/angry_levitation_death.lua
@@ -6,6 +6,9 @@ function death( damage_type_bit_field, damage_message, entity_thats_responsible,
 	
 	SetRandomSeed( GameGetFrameNum(), pos_x + pos_y + entity_id )
 	
+	local perk_flag = "PERK_PICKED_HOVER_BOOST"
+	local pickup_count = tonumber( GlobalsGetValue( perk_flag .. "_PICKUP_COUNT", "0" ) ) + 1
+	
 	local player_id = 0
 	
 	local models = EntityGetComponent( entity_id, "VariableStorageComponent" )
@@ -21,10 +24,11 @@ function death( damage_type_bit_field, damage_message, entity_thats_responsible,
 		
 		if ( comp ~= nil ) then
 			local flight = ComponentGetValue2( comp, "mFlyingTimeLeft" )
-			local maxflight = ComponentGetValue2( comp, "fly_time_max" )
+			local maxflight = ComponentGetValue2( comp, "fly_time_max" ) or 3.0
 			
-			-- print( tostring(flight) .. ", " .. tostring(maxflight))
+			maxflight = 2 ^ pickup_count + ( 2 ^ ( pickup_count - 1 ) )
 			
+			-- print( tostring(flight) .. ", " .. tostring(maxflight))
 			flight = math.min( maxflight, flight + 1.2 )
 			
 			ComponentSetValue2( comp, "mFlyingTimeLeft", flight )
diff --git a/scripts/perks/perk_gamble_spawn.lua b/scripts/perks/perk_gamble_spawn.lua
index 694d141..e52e7dc 100644
--- a/scripts/perks/perk_gamble_spawn.lua
+++ b/scripts/perks/perk_gamble_spawn.lua
@@ -4,18 +4,22 @@ dofile( "data/scripts/perks/perk.lua" )
 
 local entity_id = GetUpdatedEntityID()
 local x, y = EntityGetTransform(entity_id)
+local player = EntityGetClosestWithTag(x, y, "player_unit")
 
-local w = 10
-local perks = {}
-perks[1] = perk_spawn_random(x - w, y - 10)
-perks[2] = perk_spawn_random(x + w, y - 10)
-
-for _,v in ipairs(perks) do
-	EntityAddComponent(v, "VariableStorageComponent", 
-	{ 
-		name = "perk_dont_remove_others",
-		value_bool = "1",
-	} )
+local count = 2
+while count > 0 do
+	local pid = perk_spawn_random(x,y)
+	-- rerandomize if picked perk is gamble
+	component_read( get_variable_storage_component(pid, "perk_id"), { value_string = "" }, function(comp)
+		print(comp.value_string)
+		if comp.value_string ~= "GAMBLE" then
+			perk_pickup(pid, player, "", false, false )
+			count = count - 1
+		else
+			--print("Gamble perk spawned another Gamble. Rerandomizing...")
+			EntityKill(pid)
+		end
+	end)
 end
 
 EntityKill(entity_id)
diff --git a/scripts/perks/perk_list.lua b/scripts/perks/perk_list.lua
index ec53058..348eb69 100644
--- a/scripts/perks/perk_list.lua
+++ b/scripts/perks/perk_list.lua
@@ -1455,6 +1455,44 @@ perk_list =
 			--GenomeSetHerdId( entity_who_picked, "rat" )
 		end,
 	},
+	{
+		id = "CORDYCEPS",
+		ui_name = "$perk_cordyceps",
+		ui_description = "$perkdesc_cordyceps",
+		ui_icon = "data/ui_gfx/perk_icons/cordyceps.png",
+		perk_icon = "data/items_gfx/perks/cordyceps.png",
+		stackable = STACKABLE_NO,
+		func = function( entity_perk_item, entity_who_picked, item_name )
+		
+			EntityAddComponent( entity_who_picked, "LuaComponent", 
+			{ 
+				script_source_file = "data/scripts/perks/cordyceps.lua",
+				execute_every_n_frame = "20",
+			} )
+			
+			if ( GameHasFlagRun( "player_status_cordyceps" ) == false ) then
+				GameAddFlagRun( "player_status_cordyceps" )
+				local funginess = tonumber( GlobalsGetValue( "PLAYER_FUNGAL_LEVEL", "0" ) )
+				funginess = funginess + 1
+				GlobalsSetValue( "PLAYER_FUNGAL_LEVEL", tostring( funginess ) )
+				
+				if ( funginess == 3 ) then
+					EntitySetComponentsWithTagEnabled( entity_who_picked, "player_hat", true )
+					
+					AddFlagPersistent( "player_status_funky" )
+					
+					local damagemodels = EntityGetComponent( entity_who_picked, "DamageModelComponent" )
+					if( damagemodels ~= nil ) then
+						for i,damagemodel in ipairs(damagemodels) do
+							local explosion_resistance = tonumber(ComponentObjectGetValue( damagemodel, "damage_multipliers", "explosion" ))
+							explosion_resistance = explosion_resistance * 0.9
+							ComponentObjectSetValue( damagemodel, "damage_multipliers", "explosion", tostring(explosion_resistance) )
+						end
+					end
+				end
+			end
+		end,
+	},
 	{
 		id = "MOLD",
 		ui_name = "$perk_mold",
@@ -1468,6 +1506,28 @@ perk_list =
 			EntityAddChild( entity_who_picked, child_id )
 			
 			EntityLoad( "data/entities/items/pickup/potion_slime.xml", x, y )
+			
+			if ( GameHasFlagRun( "player_status_mold" ) == false ) then
+				GameAddFlagRun( "player_status_mold" )
+				local funginess = tonumber( GlobalsGetValue( "PLAYER_FUNGAL_LEVEL", "0" ) )
+				funginess = funginess + 1
+				GlobalsSetValue( "PLAYER_FUNGAL_LEVEL", tostring( funginess ) )
+				
+				if ( funginess == 3 ) then
+					EntitySetComponentsWithTagEnabled( entity_who_picked, "player_hat", true )
+					
+					AddFlagPersistent( "player_status_funky" )
+					
+					local damagemodels = EntityGetComponent( entity_who_picked, "DamageModelComponent" )
+					if( damagemodels ~= nil ) then
+						for i,damagemodel in ipairs(damagemodels) do
+							local explosion_resistance = tonumber(ComponentObjectGetValue( damagemodel, "damage_multipliers", "explosion" ))
+							explosion_resistance = explosion_resistance * 0.9
+							ComponentObjectSetValue( damagemodel, "damage_multipliers", "explosion", tostring(explosion_resistance) )
+						end
+					end
+				end
+			end
 		end,
 	},
 	{
@@ -1546,6 +1606,43 @@ perk_list =
 			EntityAddChild( entity_who_picked, child_id )
 		end,
 	},
+	{
+		id = "FUNGAL_DISEASE",
+		ui_name = "$perk_fungal_disease",
+		ui_description = "$perkdesc_fungal_disease",
+		ui_icon = "data/ui_gfx/perk_icons/fungal_disease.png",
+		perk_icon = "data/items_gfx/perks/fungal_disease.png",
+		stackable = STACKABLE_YES,
+		stackable_is_rare = true,
+		stackable_maximum = 3,
+		func = function( entity_perk_item, entity_who_picked, item_name )
+			local x,y = EntityGetTransform( entity_who_picked )
+			local child_id = EntityLoad( "data/entities/misc/perks/fungal_disease.xml", x, y )
+			EntityAddChild( entity_who_picked, child_id )
+			
+			if ( GameHasFlagRun( "player_status_fungal_disease" ) == false ) then
+				GameAddFlagRun( "player_status_fungal_disease" )
+				local funginess = tonumber( GlobalsGetValue( "PLAYER_FUNGAL_LEVEL", "0" ) )
+				funginess = funginess + 1
+				GlobalsSetValue( "PLAYER_FUNGAL_LEVEL", tostring( funginess ) )
+				
+				if ( funginess == 3 ) then
+					EntitySetComponentsWithTagEnabled( entity_who_picked, "player_hat", true )
+					
+					AddFlagPersistent( "player_status_funky" )
+					
+					local damagemodels = EntityGetComponent( entity_who_picked, "DamageModelComponent" )
+					if( damagemodels ~= nil ) then
+						for i,damagemodel in ipairs(damagemodels) do
+							local explosion_resistance = tonumber(ComponentObjectGetValue( damagemodel, "damage_multipliers", "explosion" ))
+							explosion_resistance = explosion_resistance * 0.9
+							ComponentObjectSetValue( damagemodel, "damage_multipliers", "explosion", tostring(explosion_resistance) )
+						end
+					end
+				end
+			end
+		end,
+	},
 	{
 		id = "PROJECTILE_SLOW_FIELD",
 		ui_name = "$perk_projectile_slow_field",
@@ -1654,8 +1751,8 @@ perk_list =
 					local platformingcomponents = EntityGetComponent( entity_who_picked, "CharacterDataComponent" )
 					if( platformingcomponents ~= nil ) then
 						for i,component in ipairs(platformingcomponents) do
-							local fly_time = ComponentGetValue2( component, "fly_time_max" ) * 1.15
-							ComponentSetValue2( component, "fly_time_max", fly_time )
+							local fly_time = ComponentGetValue2( component, "fly_recharge_spd" ) * 1.15
+							ComponentSetValue2( component, "fly_recharge_spd", fly_time )
 						end
 					end
 				end
@@ -1693,8 +1790,8 @@ perk_list =
 					local platformingcomponents = EntityGetComponent( entity_who_picked, "CharacterDataComponent" )
 					if( platformingcomponents ~= nil ) then
 						for i,component in ipairs(platformingcomponents) do
-							local fly_time = ComponentGetValue2( component, "fly_time_max" ) * 1.15
-							ComponentSetValue2( component, "fly_time_max", fly_time )
+							local fly_time = ComponentGetValue2( component, "fly_recharge_spd" ) * 1.15
+							ComponentSetValue2( component, "fly_recharge_spd", fly_time )
 						end
 					end
 				end
@@ -1733,8 +1830,8 @@ perk_list =
 					local platformingcomponents = EntityGetComponent( entity_who_picked, "CharacterDataComponent" )
 					if( platformingcomponents ~= nil ) then
 						for i,component in ipairs(platformingcomponents) do
-							local fly_time = ComponentGetValue2( component, "fly_time_max" ) * 1.15
-							ComponentSetValue2( component, "fly_time_max", fly_time )
+							local fly_time = ComponentGetValue2( component, "fly_recharge_spd" ) * 1.15
+							ComponentSetValue2( component, "fly_recharge_spd", fly_time )
 						end
 					end
 				end
diff --git a/scripts/perks/plague_rats_init.lua b/scripts/perks/plague_rats_init.lua
index 498e266..6fd9a4a 100644
--- a/scripts/perks/plague_rats_init.lua
+++ b/scripts/perks/plague_rats_init.lua
@@ -7,6 +7,7 @@ local extra_hp = math.max( 0, pos_y * 0.0002 )
 local extra_damage = math.max( 0, pos_y * 0.0001 )
 	
 EntityRemoveTag( entity_id, "homing_target" )
+EntityRemoveTag( entity_id, "enemy" )
 
 edit_component( entity_id, "DamageModelComponent", function(comp,vars)
 	local hp = tonumber(ComponentGetValue( comp, "hp"))
diff --git a/scripts/projectiles/homing_area.lua b/scripts/projectiles/homing_area.lua
index 86cde04..e88e161 100644
--- a/scripts/projectiles/homing_area.lua
+++ b/scripts/projectiles/homing_area.lua
@@ -11,7 +11,7 @@ if ( comp ~= nil ) then
 	local target = ComponentGetValue2( comp, "mWhoShot" )
 	
 	for i,v in ipairs( targets ) do
-		if ( v ~= target ) then
+		if ( v ~= target ) and ( GameGetGameEffect( v, "CHARM" ) == 0 ) and ( EntityGetHerdRelation( target, v ) < 60 ) then
 			local tx, ty = EntityGetFirstHitboxCenter( v )
 			
 			EntitySetTransform( root_id, tx, ty )
diff --git a/scripts/streaming_integration/event_list.lua b/scripts/streaming_integration/event_list.lua
index 01c6a3b..7db9ddc 100644
--- a/scripts/streaming_integration/event_list.lua
+++ b/scripts/streaming_integration/event_list.lua
@@ -2151,6 +2151,21 @@ streaming_events =
 			end
 		end,
 	},
+	{
+		id = "ALL_ACCESS_TELEPORT",
+		ui_name = "$streamingevent_all_access_teleport",
+		ui_description = "$streamingeventdesc_all_access_teleport",
+		ui_icon = "data/ui_gfx/streaming_event_icons/speedy_enemies.png",
+		ui_author = STREAMING_EVENT_AUTHOR_NOLLAGAMES,
+		weight = 0.5,
+		kind = STREAMING_EVENT_BAD,
+		action = function(event)
+			for i,entity_id in pairs( get_enemies_in_radius(500) ) do
+				EntityRemoveTag( entity_id, "teleportable_NOT" )
+				EntityAddTag( entity_id, "teleportable" )
+			end
+		end,
+	},
 	{
 		id = "HOLIDAY_MOOD",
 		ui_name = "$streamingevent_holiday_mood",
diff --git a/ui_gfx/decorations/3piece_fungal_shift.png b/ui_gfx/decorations/3piece_fungal_shift.png
index 143870d..9a3ed4a 100644
Binary files a/ui_gfx/decorations/3piece_fungal_shift.png and b/ui_gfx/decorations/3piece_fungal_shift.png differ
