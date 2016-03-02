# Housin Draft Documentation

## Table of contents

* [1.Introduction](#1introduction)
* [2.Objective](#2objective)
* [3.Search engine](#3search-engine)
 * [3.1.Payment type](#31payment-type)
 * [3.2.Location](#32location)
 * [3.3.Property type](#33property-type)
 * [3.4.Room types](#34room-types)
* [4.Floor plans](#4floor-plans)
 * [4.1.Room types](#41room-types)

## 1.Introduction

The following documentation explains the idea, major features, components, technologies and other information regarding the build process for project Housin, which name might change in the future.

It is intended as a guide on how to build it, and what needs to be built for this project to be successful, although any information written in this draft may change if the general direction of the project requires it.

## 2.Objective

Project Housin is designed for people who wishes to buy, rent or sell real estate properties. It aims to have a powerful search engine, both for specific and accurate data. People who wishes to sell or rent a property needs to specify its type, like a house or apartment, and provide its floor plan. By creating an accurate floor plan and defining room types, such as bathroom, kitchen or dorms it is possible to then find homes with certain parameters, such as number of bedrooms, size of the kitchen, etc.

## 3.Search engine

The most important part of this application is its search engine. Anyone who wishes to buy or rent someone else's real state property should be able to choose the elements suited to their needs in order to search and find what they are looking for. The main search points are payment type, location, property type and rooms.

### 3.1.Payment type

This section refers to the types a building can be sold or rented. When selling a property, a single price must be set, and that's the final price for it. However, when people buys real state, they often take out a loan to pay for it; and are able to sell such property, and the buyer will inherit the loan. This sometimes causes problems on the selling sites, as only a single value is shown, and sometimes is the up-front value of the property and not the total. It is important that the search engine returns the real total value, and separates the up-front price and the loan. Also, some companies will sell properties before they are completed; because the floor plan is available, selling this way should be allowed in the application, specifying when the property will be finished.
There are two types of renting, with furniture, or without. When renting houses with furniture, a list of such objects has to be specified, and included in the search engine. Someone should be able to search a house for rent, with TV and dishwasher. Also, rentals may have special contracts that should be fulfilled when renting a property, such as minimal stay time, payment options and availability times. These should also be reflected in the search engine.
Lastly, there is a special type of rental, called BnB (bread and breakfast) that allows users to rent some part of the house or apartment. These areas must be specified in the floor plan, along with the owner private and shared areas of the property; but works similar to a rent.
There are special plans for people who wishes to buy properties, but cannot afford it at the moment, called rental with purchase option. Rentals, with or without furniture might have this option as normal rents, with specifications on how to make the purchase.
A property might be used for rental (with and without furniture), purchase and BnB at the same time, however it will need to have a floor plan for each. These will be linked to the property and shared in the property information, should the user selects it.
Sometimes, garages are sold or rented apart from a property. In these cases, a floor plan must be created for it, specifying the size of the garage spot (or building) and set its payment type (please, do not use BnB here).

To summarize, the initial payment types are:
.Purchase (Total price shown, loans and up-front payments in details)
.Rent with furniture (yearly, monthly and daily rent, with the furnitures, buy option available)
.Rent without forniture(yearly, monthly and daily rent, buy option available)
.BnB (yearly, monthly and daily rent, with furnitures)

### 3.2.Location

Probably the most important thing an immovable has is its location. Most search engines will look for country, state and city. In some cases, this information may not be too accurate, as one city may be close to another, and their boundaries might be blurry. If left to a map engine to decide the city in which the property falls, buildings close to, but not exactly in a location may be left behind in a search result, while if left to the user, they might lie on the city name, in order for their property to show on the results. For this reason, users will have the obligation of adding a not exact (to avoid private issues), but at least 100m accurate geo-location, and the search engine will ask for a geo-location and a radius. All properties that matches the search criteria within that radius (and some more) will be shown in the search results.

### 3.3.Property type

The definition of a real state property is pretty wide. It could refer to a whole building, a house or simply an apartment inside a building, or a building block; lets not forget BnB, where only a room is for rent. For this reason, it is important to specify exactly what is being for sale. Apartments differ from houses by being several of them inside a building. This means apartments have shared spaces, and often elevators or stairs are needed to reach it. Houses on the other hand, have usually non-shared spaces, no need for stairs and can include yards. However, combination of these element exists, like houses with stairs and shared spaces with other houses. For this reason, the property type will not be defined in the application. Instead, the floor plan must specify its floor number, and the user may search only for floor plans of floor 0. This will return apartments that are on the base floor of the building, or apartment blocks that have more apartments on top. This may actually be productive, as users might choose houses over apartments because they don't want to use stairs, while being at floor 0 means there are no (long) stairs into the apartment. If the user also wants house-like things like a yard, he can specify it on the search terms, like has_yard.

### 3.4.Room types

Search queries will be defined by the number, size and type of rooms or zones within a property. These types will play an important role for defining the features of a home. Room types needs to fit the users request as accurately as possible. This means different payment types should include different types of rooms for better search results. For example, a house can have a living room, 2 bedrooms, 1 bathroom, 1 kitchen and a study. When renting this house for summer vacation, it is important to separate the bedrooms from the study, as bedrooms will have beds, while the study will not. However, when selling the house without furniture, it doesn't matter what the rooms were used for, as if the study is large enough (we do have the size of the room) it can become a bedroom (or another type) for the new owners.
To fix the above dilemma, rooms will have groups and sub-groups. Bedrooms, playrooms, studies ,etc will go under the room group, while living rooms, halls, dinner rooms, etc will go under the common space group. Bathrooms and kitchens may need better definitions, as most bathrooms are defined by having at least a toilet and a sink, a room with a bidet and a shower may be declared as a bathroom as well. For this, a user who wants to find a home with two bathrooms (each with a toilet and a shower) should look instead for two toilets and two showers; looking for 2 bathrooms is optional, but 2 toilets in a single room should be too uncommon). Bathrooms should be under hygiene rooms, along with en suite bathrooms, Jack and Jill bathrooms, wetrooms and laundry rooms. Kitchens are defined by having cookware and sometimes a skink. It has to be enforced on floor plan creators to add the sink if it has one, but this will not appear on the search engine (it can be found using sinks = number of bathrooms + 1, but this might be inaccurate). Kitchens will fall into cooking rooms categories, along side barbecues.
Exterior Areas defines things outside the house, such as playgrounds, yards and gardens.
Garages and parking lots comes into the Vehicle Access group. This group must garantee that the area defined has connectivity to an outside route or street.
A special group exists for shared spaces with other neighbors. These include common halls, playgrounds and gyms.
Stairs goes into the Accessibility group, along with steps, ramps, elevators and roads. Note that the shared group have its own set of accesibility zones called Shared Accessibility. Accessibility areas do not count thowards the total living area, however, unlike their shared counterparts, they are considered part of the property.

Here is a summary of room types to include in the application:
* Private Rooms
 * Bedroom
 * Study
 * Library
 * Playroom
 * Storage Room
 * Gym
* Common Space
 * Hall
 * Living Room
 * Diner Room
 * Relax Room
* Hygiene Rooms
 * Bathroom
 * Bathroom (en suite)
 * Bathroom (Jack and Jill)
 * Wetroom
 * Shower Room
 * Laundry Room
 * Interior Pool Area
* Cooking Space
 * Kitchen
 * Kitchenette
 * Interior Barbacue
* Exterior Area
 * Backyard
 * Yard
 * Garden
 * Playground
 * Pool Area
 * Barbacue
* Vehicle Access
 * Garage
 * Parking Lot
 * Parking Roof
* Accessibility
 * Steps
 * Stairs
 * Ladder
 * Elevator
 * Ramp
* Shared Space
 * Shared Hall
 * Shared Playground
 * Shared Pool Area
 * Shared Gym
* Shared Accessibility
 * Shared Steps
 * Shared Stairs
 * Shared Ladder
 * Shared Elevator
 * Shared Ramp
 
## 4.Floor plans

The main tool for finding accurate data of a real state property is thru its floor plan or blueprint. Although some of the data within a floor plan is not needed for accurate search, such as wall thickness or precise room position, it's important to add label to rooms, as most searches are regarding room proposes.