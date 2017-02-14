# shk_pos_functions
Shuko Position Function Library

  SHK_pos_functions

  Version 1.0
  Author: Shuko (shuko@quakenet, miika@miikajarvinen.fi)
  Contributors: Cool=Azroul13, Hatifnat, Celludriel

  Original Shuko Forum: http://forums.bistudio.com/showthread.php?162695-SHK_pos
  Celludriel Forum: https://forums.bistudio.com/topic/202195-release-shk_pos_functions
  
    Marker Based Selection
    Required Parameters:
      0 String   Area marker's name.

    Optional Parameters:
      1 Number            Water position. Default is only land positions allowed.
                            0   Find closest land. Search outwards 360 degrees (20 degree steps) and 20m steps.
                            1   Allow water positions.
                            2   Find only water positions.
      2 Array or String   One or multiple blacklist area markers which are excluded from the main marker area.
      3 Array, Number, Object or Vehicle Type         Force finding large enough empty position.
                            0   Max range from the selection position to look for empty space. Default is 200.
                            1   Vehicle or vehicle type to fit into an empty space.

                            Examples:
                              [...,[300,heli]]       Array with distance and vehicle object.
                              [...,350]              Only distance given
                              [...,(typeof heli)]    Only vehicle type given
                              [...,heli]             Only vehicle object given

    Position Based Selection
    Required Parameters:
      0 Object or Position  Anchor point from where the relative position is calculated from.
      1 Array or Number     Distance from anchor.

    Optional Parameters:
      2 Array of Number     Direction from anchor. Default is random between 0 and 360.
      3 Number              Water position. Default is only land positions allowed.
                              0   Find closest land. Search outwards 360 degrees (20 degree steps) and 20m steps.
                              1   Allow water positions.
                              2   Find only water positions.
      4 Array               Road positions.
                              0  Number  Road position forcing. Default is 0.
                                   0    Do not search for road positions.
                                   1    Find closest road position. Return the generated random position if none found.
                                   2    Find closest road position. Return empty array if none found.
                              1  Number   Road search range. Default is 200m.
      5 Array, Number, Object or Vehicle Type         Force finding large enough empty position.
                              0   Max range from the selection position to look for empty space. Default is 200.
                              1   Vehicle or vehicle type to fit into an empty space.

                            Examples:
                              [...,[300,heli]]       Array with distance and vehicle object.
                              [...,350]              Only distance given
                              [...,(typeof heli)]    Only vehicle type given
                              [...,heli]             Only vehicle object given

    Release download:
    https://github.com/Celludriel/shk_pos_functions/archive/1.0.0.zip
    
    Installation:
    Unpack this zip in the directory of your choice in your mission fe: shk_pos
    
    Usage:
    include CfgFunctions.hpp in description.ext:
    class CfgFunctions
    {
        ...
        #include "shk_pos\CfgFunctions.hpp"
        ...
    };
    
    Actually getting the position:
        pos = [parameters] call ShkPos_fnc_executeFindPosition;