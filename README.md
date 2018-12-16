# xiang
跳转详情
第一种方式
1第一界面点击事件跳转详情界面

     <Text
                style={{ flex: 1, fontSize: 18 }}
                onPress={() => {
                  this.props.navigation.navigate("Details", {
                    abc: item.content
                  });
                }}
              >
                {item.title}
       </Text>
  2第二界面接收详情数据
  
        import React, { Component } from "react";
        import {
          Platform,
          StyleSheet,
          Text,
          View,
          ScrollView,
          Dimensions
        } from "react-native";
        import HTML from "react-native-render-html";

    export default class Details extends Component {
      render() {
        return (
          <View style={styles.container}>
            <Text style={styles.welcome}>Welcome to React 详情!</Text>
            <ScrollView style={{ flex: 1 }}>
              <HTML
                html={this.props.navigation.getParam("abc", "abc")}
                imagesMaxWidth={Dimensions.get("window").width - 20}
              />
            </ScrollView>
          </View>
        );
      }
    }

    const styles = StyleSheet.create({
      container: {
        flex: 1,
        justifyContent: "center",
        alignItems: "center",
        backgroundColor: "#F5FCFF"
      },
      welcome: {
        fontSize: 20,
        textAlign: "center",
        margin: 10
      },
      instructions: {
        textAlign: "center",
        color: "#333333",
        marginBottom: 5
      }
    });
    
    
    
   第二种方式WebView
            1.第一界面
            
              <Text
                onPress={() => {
                  this.props.navigation.navigate("XiangQing", {
                    abc: item.link
                  });
                }}
              >
                {item.title}
              </Text>
              
   2.第二界面
   
         render() {
          var link = this.props.navigation.getParam("abc");
          return (
            <View style={styles.container}>
              <WebView source={{ uri: link }} />
            </View>
          );
        }
      
    
    
