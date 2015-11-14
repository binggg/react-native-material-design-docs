# Typography

```javascript
    import { StyleSheet } from 'react-native';
    import { typography } from 'react-native-material-design-styles';
    const typographyStyle = StyleSheet.create(typography);
```

Now we can use Material Design typography in our JSX code.

```javascript
    <Text style={[typographyStyle.paperFontHeadline, colorStyle.paperTeal500]}>Typography</Text>
    <Text style={[typographyStyle.paperFontDisplay4]}>Display4</Text>
    <Text style={typographyStyle.paperFontDisplay3}>Display3</Text>
    <Text style={typographyStyle.paperFontDisplay2}>Display2</Text>
    <Text style={typographyStyle.paperFontDisplay1}>Display1</Text>
    <Text style={typographyStyle.paperFontHeadline}>Headline</Text>
    <Text style={typographyStyle.paperFontTitle}>Title</Text>
    <Text style={typographyStyle.paperFontSubhead}>Subhead</Text>
    <Text style={typographyStyle.paperFontBody2}>Body2</Text>
    <Text style={typographyStyle.paperFontBody1}>Body1</Text>
    <Text style={typographyStyle.paperFontCaption}>Caption</Text>
    <Text style={typographyStyle.paperFontButton}>Button</Text>
    <Text style={typographyStyle.paperFontCode2}>Code2</Text>
    <Text style={typographyStyle.paperFontCode1}>Code1</Text>
```