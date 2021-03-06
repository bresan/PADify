vole_module_name("lille")
vole_module_description("Local Illuminant Estimation")
vole_module_variable("Vole_lille")

vole_add_required_dependencies("OPENCV" "BOOST" "BOOST_PROGRAM_OPTIONS" "BOOST_FILESYSTEM" "QT")
vole_add_required_modules("illumestimators" "iic_commands" "iic" "rbase" "superpixels")

vole_compile_library(

	"commands/command_color_illum_field.h" "commands/command_color_illum_field.cpp"
	"commands/command_liebv.h"             "commands/command_liebv.cpp"
	"commands/command_ltan.h"              "commands/command_ltan.cpp"
	"commands/command_tan_orig.h"          "commands/command_tan_orig.cpp"
	"commands/command_gw_orig.h"           "commands/command_gw_orig.cpp"
	"commands/command_lgrayworld.h"        "commands/command_lgrayworld.cpp"
	"commands/command_lbayesian.h"         "commands/command_lbayesian.cpp"
	"liebv_config.h"                       "liebv_config.cpp"
	"lgrayworld_config.h"                  "lgrayworld_config.cpp"
	"lbayesian_config.h"                   "lbayesian_config.cpp"
	"paint_superpixel.h"                   "paint_superpixel.cpp"

	"tan_orthodox/image.h"
	"tan_orthodox/tan_misc.h"
	"tan_orthodox/pnmfile.h"
	"tan_orthodox/zGlobal.h"
	"tan_orthodox/zImageMagick.h"
	"tan_orthodox/orthodox_tan_adapter.h"  "tan_orthodox/orthodox_tan_adapter.cpp"
	"tan_orthodox/zLightChroma.h"          "tan_orthodox/zLightChroma.cxx"
)

vole_add_command("lcolfield"   "commands/command_color_illum_field.h"    "lille::CommandColorIllumField")
vole_add_command("liebv"       "commands/command_liebv.h"                "lille::CommandLocalIebv")
vole_add_command("ltan"        "commands/command_ltan.h"                 "lille::CommandLocalTan")
vole_add_command("tanOrig"     "commands/command_tan_orig.h"             "lille::CommandTanOrig")
vole_add_command("gwOrig"      "commands/command_gw_orig.h"              "lille::CommandGrayworldOrig")
vole_add_command("lgrayworld"  "commands/command_lgrayworld.h"           "lille::CommandLocalGrayworld")
vole_add_command("lbayesian"   "commands/command_lbayesian.h"            "lille::CommandLocalBayesian")


vole_add_module()
