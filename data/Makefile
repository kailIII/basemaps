SHPTREE=shptree

all: TM_WORLD_BORDERS-0.3 ne_10m_admin_0_boundary_lines_land processed_p shoreline_300

# Implicit rules to map 'all' targets to their .shp and .qix dependencies
%: %.shp %.qix ;

.PRECIOUS: %.qix %.shp ;

%.qix: %.shp
	$(SHPTREE) $< 8

processed_p.shp: processed_p.tar.bz2
	tar xmjf processed_p.tar.bz2

shoreline_300.shp: shoreline_300.tar.bz2
	tar xmjf shoreline_300.tar.bz2

TM_WORLD_BORDERS-0.3.shp: TM_WORLD_BORDERS-0.3.zip
	unzip TM_WORLD_BORDERS-0.3.zip
	touch TM_WORLD_BORDERS-0.3.shp

ne_10m_admin_0_boundary_lines_land.shp: ne_10m_admin_0_boundary_lines_land.zip
	unzip ne_10m_admin_0_boundary_lines_land.zip
	touch ne_10m_admin_0_boundary_lines_land.shp

processed_p.tar.bz2:
	wget http://tile.openstreetmap.org/processed_p.tar.bz2

ne_10m_admin_0_boundary_lines_land.zip:
	wget http://www.naturalearthdata.com/http//www.naturalearthdata.com/download/10m/cultural/ne_10m_admin_0_boundary_lines_land.zip

shoreline_300.tar.bz2:
	wget http://tile.openstreetmap.org/shoreline_300.tar.bz2

TM_WORLD_BORDERS-0.3.zip:
	wget http://thematicmapping.org/downloads/TM_WORLD_BORDERS-0.3.zip

