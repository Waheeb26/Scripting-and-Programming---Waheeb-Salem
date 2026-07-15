# Waheeb Salem , Scripting & Programming 2026
# Project: Smart Classroom Device Manager for Bright Minds Academy

import os
import sys

# A flat dictionary (Key: Device Name , Value: Room Location)
devices = {}
device_counter = 1

# 1. Add a new device
def add_device(room):
    global device_counter
    name = f"Device {device_counter}"
    devices[name] = room
    print(f"\n'{name}' added to '{room}'.")
    device_counter = device_counter + 1

# 2. Update a device's room
def update_room(name, new_room):
    # Check directly if the key exists
    if name in devices:
        devices[name] = new_room
        print(f"\n'{name}' moved to '{new_room}'.")
    else:
        print(f"\n'{name}' not found.")

# 3. View all devices
def view_devices():
    if len(devices) == 0:
        print("\nNo devices added yet.")
    else:
        print("\n--- All Devices ---")
        # Loop through keys and values directly
        for name, room in devices.items():
            print(f"- {name} is in {room}")


# 4. Search for a device
def search_device(name):
    if name in devices:
        print(f"\nFound! {name} is located in: {devices[name]}")
    else:
        print(f"\n'{name}' not found.")


# Main menu
def main():
    while True:
        print("\n--- Bright Minds Academy Device Manager ---")
        print("1. Add a new device")
        print("2. Update device room")
        print("3. View all devices")
        print("4. Search for a device")
        print("5. Exit")

        choice = input("\nChoose an option (1-5): ")

        if choice == "1":
            room = input("Enter room location: ")
            add_device(room)

        elif choice == "2":
            name = input("Device name to update (e.g. Device 1): ")
            new_room = input("Enter new room location: ")
            update_room(name, new_room)

        elif choice == "3":
            view_devices()

        elif choice == "4":
            name = input("Device name to search (e.g. Device 1): ")
            search_device(name)

        elif choice == "5":
            print("\nGoodbye!")
            break
        else:
            print("Invalid option. Try again.")


# Run the program
main()






