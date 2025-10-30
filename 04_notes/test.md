# Transport를 serial로 변경
snap set micro-ros-agent transport="serial"

# Middleware 설정 (dds는 유효하지 않음 - eProsima 또는 CycloneDDS)
snap set micro-ros-agent middleware="eProsima"

# Serial 설정 (이미 되어 있지만 확인)
snap set micro-ros-agent device="/dev/ttyACM0"
snap set micro-ros-agent baudrate="115200"

# Verbosity (0-6, 기본값 4)
snap set micro-ros-agent verbosity="4"

# Discovery 설정
snap set micro-ros-agent discovery="false"
snap set micro-ros-agent discovery-port="7400"

# Port는 serial 모드에서는 사용 안 함 (UDP/TCP 전용)
# snap set micro-ros-agent port="8888"  # serial 사용시 불필요
