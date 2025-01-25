# TUDYSUDY
import React from "react";
import { SafeAreaView, StyleSheet, Text, View, Button } from "react-native";
import { NavigationContainer } from "@react-navigation/native";
import { createStackNavigator } from "@react-navigation/stack";

const Stack = createStackNavigator();

const HomeScreen = ({ navigation }) => (
  <SafeAreaView style={styles.container}>
    <Text style={styles.title}>Welcome to Bus Ticket Booking</Text>
    <Button
      title="Book a Ticket"
      onPress={() => navigation.navigate("Booking")}
    />
  </SafeAreaView>
);

const BookingScreen = ({ navigation }) => (
  <SafeAreaView style={styles.container}>
    <Text style={styles.title}>Choose Your Route and Date</Text>
    <Button
      title="View Available Buses"
      onPress={() => navigation.navigate("BusList")}
    />
  </SafeAreaView>
);

const BusListScreen = ({ navigation }) => (
  <SafeAreaView style={styles.container}>
    <Text style={styles.title}>Available Buses</Text>
    <Button
      title="Select Seats"
      onPress={() => navigation.navigate("SeatSelection")}
    />
  </SafeAreaView>
);

const SeatSelectionScreen = ({ navigation }) => (
  <SafeAreaView style={styles.container}>
    <Text style={styles.title}>Select Your Seat</Text>
    <Button
      title="Confirm Booking"
      onPress={() => navigation.navigate("Ticket")}
    />
  </SafeAreaView>
);

const TicketScreen = () => (
  <SafeAreaView style={styles.container}>
    <Text style={styles.title}>Your Ticket</Text>
    <Text>QR Code or Ticket Details Here</Text>
  </SafeAreaView>
);

export default function App() {
  return (
    <NavigationContainer>
      <Stack.Navigator>
        <Stack.Screen name="Home" component={HomeScreen} />
        <Stack.Screen name="Booking" component={BookingScreen} />
        <Stack.Screen name="BusList" component={BusListScreen} />
        <Stack.Screen name="SeatSelection" component={SeatSelectionScreen} />
        <Stack.Screen name="Ticket" component={TicketScreen} />
      </Stack.Navigator>
    </NavigationContainer>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: "center",
    alignItems: "center",
    padding: 16,
  },
  title: {
    fontSize: 24,
    fontWeight: "bold",
    marginBottom: 16,
  },
});
