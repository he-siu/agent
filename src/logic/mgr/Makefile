include ../../build.config

CFLAGS = $(DEFINES) $(INCLUDES)

define make_sub_dir
set -e;										\
	for subdir in $(SUBDIR); do						\
		if [ -d "$${subdir}" ]; then					\
			$(MAKE) $(@) --directory="$${subdir}"; \
		fi								\
	done
endef


SUBDIR := ctrl env log org po_etc po_fa po_fe po_in site

.PHONY: all

all:
#	$(shell mkdir lib)
	@$(make_sub_dir)
	make mgr_all
	
clean:
	@$(make_sub_dir)
	make mgr_clean
#	$(shell rm -rf lib)
	
mgr_clean:
	rm -f *.o

mgr_all:
	$(CC) $(CFLAGS) -c LogicMgrAuth.cpp
	
