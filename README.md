2. CALENDAR

node_modules/react-native-calendars/src/calendar/day/period/index.js

- Add Platform to react-native imports
- Inside the render()
{Platform.OS === 'android' ?
<View>
    <Text allowFontScaling={false} style={[textStyle, containerStyle]}>{String(this.props.children)}</Text>
</View>
:
<View style={containerStyle}>
    <Text allowFontScaling={false} style={textStyle}>{String(this.props.children)}</Text>
</View>
}

- Inside the render() the <Dot></Dot> has been recently added: check if it works
<Dot
    theme={theme}
    isMarked={marked}
    dotColor={dotColor}
/>

node_modules/react-native-calendars/src/calendar/day/period/style.js

- text object:
    text: {
      //marginTop: 7,
      // -- ADDED --
      paddingTop: 7,
      textAlign: 'center',
      // -----------
      fontSize: appStyle.textDayFontSize,
      fontFamily: appStyle.textDayFontFamily,
      fontWeight: appStyle.textDayFontWeight,
      color: appStyle.dayTextColor,
      backgroundColor: 'rgba(255, 255, 255, 0)'
    },

node_modules/react-native-calendars/src/calendar/day/basic/style.js

- Change width and height from 32 to 34
    base: {
      width: 34,
      height: 34,
      alignItems: 'center'
    },

- Change borderRadius from 16 to 17
    selected: {
      backgroundColor: appStyle.selectedDayBackgroundColor,
      borderRadius: 17
    },
    today: {
      backgroundColor: appStyle.todayBackgroundColor,
      borderRadius: 17
    },

node_modules/react-native-calendars/src/agenda/index.js

- Change calendarOffset()
  // calendarOffset() {
  //   return 96 - (this.viewHeight / 2);
  // }

  calendarOffset() {
    const offset = 100
    return offset - this.viewHeight / 2
  }