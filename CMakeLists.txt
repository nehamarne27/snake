cmake_minimum_required(VERSION 2.8.3)

project(snake)

find_package(catkin REQUIRED)

catkin_package()

find_package(roslaunch)

foreach(dir config launch meshes urdf)
	install(DIRECTORY ${dir}/
		DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/${dir})
endforeach(dir)

catkin_install_python(PROGRAMS src/FKvalidation.py src/FKandIK.py src/IK.py src/HW4_soln.py src/FKandIK.py src/FKvalidation.py src/LinearProgression.py src/LateralUndulation.py src/SideWinding.py
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
