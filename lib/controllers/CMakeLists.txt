add_library(ActuatorController STATIC)
target_sources(ActuatorController PRIVATE src/ActuatorController.cpp)
target_include_directories(ActuatorController PUBLIC include)
target_link_libraries(ActuatorController
        PUBLIC
        PID
        PRIVATE
        EncoderAbsolute_PWM
        Motor
        )
target_set_mbed_dependency(ActuatorController)

add_library(Motor STATIC)
target_sources(Motor PRIVATE src/Motor.cpp)
target_include_directories(Motor PUBLIC include)
target_set_mbed_dependency(Motor)

add_library(ServoMotor STATIC)
target_sources(ServoMotor PRIVATE src/ServoMotor.cpp)
target_include_directories(ServoMotor PUBLIC include)
target_link_libraries(ServoMotor PRIVATE ContServo Motor)
target_set_mbed_dependency(ServoMotor)
