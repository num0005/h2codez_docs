title:      Extra Commands
desc:       Only one of these work really but lets preserve them anyways.
template:   document
nav:        H2Tool>Extra Commands
percent:    100
date:       2020/02/19
authors:    General_101

By typing in "h2tool extra-commands" you will get the option to use some of the dev commands in H2Tool. You can use "h2tool extra-commands-list" but here they will be listed and explained if possible.

  fix-weapons
  
    description: your momma
	
        usage: Unknown
		
  convert-accel-screens
  
    description: loads all unit graphs and convert the acceleration screen data
	
        usage: Unknown
		
  update-animations
  
    description: loads all animation graphs to do any post-process updating needed
	
        usage: Unknown
		
  clear-animation-production-flags
  
    description: loads all animation graphs and clears their post process flag
	
        usage: Unknown
		
  print-weapon-labels
  
    description: converts old string_id's in weapons to class and label names
	
        usage: Unknown
		
  rename-weapon-labels
  
    description: converts old string_id's in weapons to class and label names
	
        usage: Unknown
		
  find-all-objects-inheriting-markers
  
    description: searches through all tags (ugh!) for object tags inheriting parent markers
	
        usage: Unknown
		
  update-scenario-ai-anims
  
    description: updates all tag references to old animation tags
	
        usage: Unknown
		
  update-scenario-anims
  
    description: updates all tag references to old animation tags
	
        usage: Unknown
		
  update-widget-anims
  
    description: updates all tag references to old animation tags
	
        usage: Unknown
		
  update-weapon-anims
  
    description: updates all tag references to old animation tags
	
        usage: Unknown
		
  update-sky-anims
  
    description: updates all tag references to old animation tags
	
        usage: Unknown
		
  fix-skies
  
    description: ...
	
        usage: Unknown
		
  fix-planar-fog
  
    description: ...
	
        usage: Unknown
		
  update-model-anims
  
    description: updates all tag references to old animation tags
	
        usage: Unknown  
		
  blank-render-models
  
    description: replaces all render_model tags with blank ones
	
        usage: Unknown 
		
  build-models
  
    description: builds model tags from objects
	
        usage: Unknown    
		
  find-blank-models
  
    description: builds model tags from objects
	
        usage: Unknown
		
  fix-collision-node-bsps
  
    description: fixes old collision models with bsps in their nodes
	
        usage: Unknown
		
  rename-collision-models
  
    description: renames old *.model_collision_geometry to *.collision_model
	
        usage: Unknown     
		
  find-old-objects
  
    description: finds objects with old tag references
	
        usage: Unknown     
		
  create-model-materials
  
    description: creates materials for old models
	
        usage: Unknown
		
  convert-lights
  
    description: convert all old (pre-merge) lights into new lights
	
        usage: Unknown
		
  fix-effects
  
    description: remove all effect parts with null tag references
	
        usage: Unknown     
		
  fix-lights
  
    description: ooo oo hho haaaaa! !!
	
        usage: Unknown
		
  model-shaders
  
    description: fixes render_model materials so they reference new shaders
	
        usage: Unknown 
		
  structure-shaders
  
    description: fixes structure materials so they reference new shaders
	
        usage: Unknown 
		
  fix-structures-for-fog
  
    description: fixes structure bsp cluster->scenario_atmospheric_fog_palette_index
	
        usage: Unknown     
		
  check-vehicles
  
    description: reports human plane vehicles
	
        usage: Unknown 
		
  fix-damage
  
    description: converts damage_resistance to damage_info
	
        usage: Unknown 
		
  check-shader-passes
  
    description: iterate over shader passes and do something useful
	
        usage: Unknown 
		
  check-shader-templates
  
    description: iterate over shader templates and do something useful
	
        usage: Unknown
		
  check-light-responses
  
    description: iterate over light responses and do something useful
	
        usage: Unknown 
		
  check-lens-flares
  
    description: iterate over lens flares and do something useful
	
        usage: Unknown
		
  fix-shader-passes
  
    description: iterate over shader passes and do something useful
	
        usage: Unknown
		
  fix-shader-templates
  
    description: iterate over shader templates and do something useful
	
        usage: Unknown
		
  fix-light-responses
  
    description: iterate over light responses and do something useful
	
        usage: Unknown
		
  fix-decals
  
    description: iterate over decals and do something useful
	
        usage: Unknown
		
  fix-shaders
  
    description: iterate over shaders and do something useful
	
        usage: Unknown
		
  fix-bitmaps
  
    description: iterate over bitmaps and do something useful
	
        usage: Unknown
		
  fix-model-damage2
  
    description: inverts a damage threshold
	
        usage: Unknown
		
  fix-physics-models
  
    description: upgrading to havok2.2
	
        usage: Unknown
		
  fix-render-model-compound-nodes
  
    description: taco salad LIVES!!
	
        usage: Unknown
		
  fix-scenery-objects
  
    description:
	
        usage: Unknown
		
  fix-structure-new-visibility
  
    description:
	
        usage: Unknown
		
  check-structure-materials
  
    description:
	
        usage: Unknown
		
  check-unused-variants
  
    description: look for models with nonzero pad in variants
	
        usage: Unknown
		
  fix-time-effects
  
    description: perform time conversion on all effects
	
        usage: Unknown
		
  fix-time-globals
  
    description: perform time conversion on game globals
	
        usage: Unknown
		
  fix-time-units
  
    description: perform time conversion on all units
	
        usage: Unknown
		
  fix-time-bipeds
  
    description: perform time conversion on all bipeds
	
        usage: Unknown
		
  fix-time-vehicles
  
    description: perform time conversion on all vehicles
	
        usage: Unknown
		
  fix-time-creatures
  
    description: perform time conversion on all creatures
	
        usage: Unknown
		
  count-scripts
  
    description: count number of script threads required
	
        usage: h2tool extra-commands count-scripts (path to scenario file without file extension ex. scenarios\multi\arena\arena)
		
  remove-weapon-huds
  
    description: count number of script threads required
	
        usage: Unknown     
		
  remove-biped-huds
  
    description: count number of script threads required
	
        usage: Unknown
		
  remove-vehicle-huds
  
    description: count number of script threads required
	
        usage: Unknown
		
  fix-lightmaps
  
    description: delete all lightmap groups
	
        usage: Unknown
		
  new-renderer-structure
  
    description: fixes structure bsps with data for the new renderer
	
        usage: Unknown
		
  new-renderer-render-models
  
    description: fixes render models with data for the new renderer
	
        usage: Unknown
		
  fix-particles
  
    description: loads and saves all particle tags to get around versioning bug
	
        usage: Unknown
		
  reimport-structure-bsps
  
    description: reimports all checked out structure bsps
	
        usage: Unknown
		
  reimport-collision-models
  
    description: reimports all checked out collision models
	
        usage: Unknown
		
  copy-out-pixel-shaders
  
    description: copies out pixel shaders within shader passes to separate files
	
        usage: Unknown
		
  report-bitmap-formats
  
    description: reports the format information for all bitmap tags
	
        usage: Unknown
		
  make-bitmaps-pc-safe
  
    description: fix bitmap tags to not use Xbox specific formats
	
        usage: Unknown
		
  unpalettize-lightmaps
 
    description: what it says
	
        usage: Unknown
		
  dx9-vertex-shader-refs
  
    description: make sure all vertex shaders are referenced out of the dx9 directory
	
        usage: Unknown
