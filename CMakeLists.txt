#####################################################################
# Automaton library
#####################################################################
set( AUTOMATON_BASE_SRC_FILES
        src/Atm_analog.cpp
        src/Atm_bit.cpp
        src/Atm_button.cpp
        src/Atm_command.cpp
        src/Atm_comparator.cpp
        src/atm_connector.cpp
        src/Atm_controller.cpp
        src/atm_counter.cpp
        src/Atm_digital.cpp
        src/Atm_encoder.cpp
        src/Atm_fade.cpp
        src/Atm_fan.cpp
        src/Atm_led.cpp
        #TODO: FIX player
        #        src/Atm_player.cpp
        src/Atm_step.cpp
        src/Atm_timer.cpp
        src/atm_timer_millis.cpp
        src/Automaton.cpp
        src/Machine.cpp

        src/WMath.cpp
        )


add_avr_library( automaton-base ${AUTOMATON_BASE_SRC_FILES} )

avr_target_include_common_directories(
        automaton-base PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}/src
)

avr_target_link_libraries(
        automaton-base
        avrtools
        avrtools-usart0
        avrtools-a2d
        avrtools-pwm
)

message( STATUS "AUTOMATON: ${CMAKE_CURRENT_SOURCE_DIR}" )
message( ">\tCurrent build type: ${CMAKE_BUILD_TYPE}" )