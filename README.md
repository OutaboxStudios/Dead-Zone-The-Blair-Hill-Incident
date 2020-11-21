# Dead-Zone-The-Blair-Hill-Incident
Featured game
Dead Zone: The Blair Hill Incident is an adventure survival horror game that is in current development by Outabox Studios and scheduled for a late October 2022 release on PC, PlayStation and Xbox. The story will take place on a fictional secluded island in the middle of the Pacific Ocean. The majority of the gameplay however will take place within a hidden Community Estate known as Blair Hill. It will be behind these gates where the player’s given character will have to endure some brutal and outright terrifying moments while uncovering the truth of what plagues the island. The game will embody some factors of an open world in order to enable exploration within the surrounding areas of Blair Hill which will be crucial to puzzle solving and obtaining items, objects and collectables. There will be instances where the player’s character/characters are forced into dark tunnels, narrow spaces, high towers, deep bodies of water, cold caves, haunted buildings, streets filled with undead hordes, locations with angry and unsettled mobs, unavoidable boss fights and so much more. The game will jump between third and first person view depending on the situation at hand. Outabox Studios plan to expand on the survival difficulty modes and unlockable postgame missions which might include new characters and monsters. An Undead quest where the player gets to experience the zombie life in a zombie to zombie setting is also in the mix.

 Players will assume the roles of numerous characters throughout the Blair Hill Incident story line. These character roles will be split into three states: Stages/Levels/Moments which are set either before, during or after the Incident took place. Not only will these different states be used to give more insight to the player on where certain items, objects, clues, information or passwords may be located, but it will also give the player a better perception on how the story unfolds from different perspectives as the player pieces the story together. The player will have full control of each character’s choices as well as their actions which will ultimately impact the story line for another character. Who survives and doesn’t will be up to the player’s actions and skills. Outabox Studios are focused on giving the player an experience of a lifetime and intend to keep the gameplay within the story as dark, twisted, exciting, mysterious, fear-filled and enjoyable as possible at all times.

 Dead Zone’s locations for now include the following, Blair Beachfront, Blair Hill, Staff Village, The Woods, The Forrest, The Blair Mountains, The sunken tunnels and The Scaled Islands which surround the main Island. To follow are some declassified areas such as landmarks and buildings that can be found within the mentioned locations.

Blair Beachfront: Blair Beachfront Hotel, Beach Patrol Offices, Beachfront Apartments, Aquarium, Local Beach North, Local Beach West, Sally’s Skate Park, Sunny Showers and Beauty Parlour, Restaurant Drive, Beachfront Shops, Blair Mouth, Relic Underwater Expedition and Tours, Rad Steve’s Surf Shop, The Layover, The Lighthouse, Sherry’s Boat Yard and The Peer.

Blair Hill: The Suburbs, Upper-class Housing, Elite Housing, Community Hall, Church, Water Purification Plant, Veterinary, Pharmacy, Hospital, Primary School, High School, University, Sports Centre, Central Offices, Casino, Mall, Carwash, Upper Park, Mid Park, Lower Park, Zoo, Court, Sheriff’s Office, Fire Department and Security Headquarters.

Staff Village: Villas and Housing Projects, Barracks, Security Base Alpha, Shopping Centre, Clinic, Central Park, Flee Market, Sewerage Plant, West and South Vineyard, Slaughter House, Community Library and Staff Village Community Hall.

The Woods: Security Base Bravo, Beekeeping grounds, Mad Marcie’s Moonshine Distillery, The Hunting grounds, Off-road Track, Dave’s Erection and Building Contractors Site and The Southern Nature Reserve.

The Forest: Nature Reserve Headquarters, Security Base Charlie, Chelsea’s Peak, Blair Falls, Blair River, Old Grounds, Native Memorial Grave Site, Canopy Tours, Dan’s Fishing Court and The Eastern Nature Reserve.

The Blair Mountains: Blair Peak, The Lookout, The Summit, Tanya’s Extreme Endurance Track, Blair Caves, Vic’s Bed and Breakfast, Security Base Delta, Green Energy Plant, Native Memorial Art Site and Baegon’s Nest.

The Sunken Tunnels: Security Base Echo, Tunnel Entrance East, Security Base Foxtrot, Tunnel Entrance South, Tunnel Hall, Underground Security Platform Alpha, Fork One, Fork Two, Fork Three, Tunnel Maze, Underground Security Platform Bravo, Mineral Extraction Point A, Underground Security Platform Charlie, Mineral Extraction Point B, Mineral Extraction Point C, Fork Four, Underground Security Platform Echo, Tunnel One Exit, Security Base Golf, Tunnel Two Exit, Security Base Hotel, Tunnel Exit Three and The Collection Pit.

The Scaled Islands: Marnabak’s Island, Marnabak’s Bakery, Marnabak’s Hut, Marnabak’s Stash, Marnabak’s Peer and Marnabak’s Cult. The High Bridge, Water Tower One, Scaled Island Two, The Writer’s Manor, The Green House and Warthog’s Pit. The Low Bridge, Water Tower Two, Scaled Island Three, Old Cottage and Allister’s Gun Range. The Scattered Bridge, Water Tower Three, Scaled Island Four, Marnabak’s Family Grave Site, Ruined Church, Ella’s Farm and Ella’s Tree House Lodge. The Haunted Bridge, The Hydro Conversion Tower, The Scarred Island, Old Ruins, Dark Forest, Haunted Cove, Splinter Village, Anna’s Hall, The Sunken Bridge, The Nowhere Island, Secret Facility and Test Site.

 The following source code is meant for the unreal engine
 
 Character Movement Source Code: Lana_Slade:The Blair Hill Incident-Chapter 5 (First_switch_from_third_person_to_first_person_view)
 Scene opening: Player enters Grayson Manor as Lana_Slade
 (Character_Pinned_in_mansion_on_the_hill)
 // Handles input for moving forward and backward.
UFUNCTION()
void MoveForward(float Value);

// Handles input for moving right and left.
UFUNCTION()
void MoveRight(float Value);#pragma once

#include "GameFramework/Character.h"
#include "FPSCharacter.generated.h"

UCLASS()
class FPSPROJECT_API AFPSCharacter : public ACharacter
{
    GENERATED_BODY()

public:
    // Sets default values for this character's properties
    AFPSCharacter();

protected:
    // Called when the game starts or when spawned
    virtual void BeginPlay() override;

public:
    // Called every frame
    virtual void Tick( float DeltaSeconds ) override;

    // Called to bind functionality to input
    virtual void SetupPlayerInputComponent(class UInputComponent* PlayerInputComponent) override;

    // Handles input for moving forward and backward.
    UFUNCTION()
    void MoveForward(float Value);

    // Handles input for moving right and left.
    UFUNCTION()
    void MoveRight(float Value);

};// Called to bind functionality to input
void AFPSCharacter::SetupPlayerInputComponent(class UInputComponent* PlayerInputComponent)
{
    Super::SetupPlayerInputComponent(PlayerInputComponent);

    // Set up "movement" bindings.
    PlayerInputComponent->BindAxis("MoveForward", this, &AFPSCharacter::MoveForward);
    PlayerInputComponent->BindAxis("MoveRight", this, &AFPSCharacter::MoveRight);
}void AFPSCharacter::MoveForward(float Value)
{
    // Find out which way is "forward" and record that the player wants to move that way.
    FVector Direction = FRotationMatrix(Controller->GetControlRotation()).GetScaledAxis(EAxis::X);
    AddMovementInput(Direction, Value);
}void AFPSCharacter::MoveRight(float Value)
{
    // Find out which way is "right" and record that the player wants to move that way.
    FVector Direction = FRotationMatrix(Controller->GetControlRotation()).GetScaledAxis(EAxis::Y);
    AddMovementInput(Direction, Value);
}

Note...The above source code will be modified.
