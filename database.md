# Firebase database structure
## User data
```
/users/{uid}
    - firstName: string
    - lastName: string
    - picture: string
    - role: string
    - lastLogin: timestamp

/users/{uid}/personalInfo/{personalInfoId}
    - street: string
    - number: string
    - zipCode: string
    - city: string
    - country: string
    - phoneNumber: string
    - email: string
    - birthday: timestamp
    - gender: string

/users/{uid}/personalInfo/{personalInfoId}/emergencyContacts/{emergencyContactId}
    - firstName: string
    - lastName: string
    - phoneNumber: string
```
## Club data
```
/clubs/{clubId}
    - name: string

/clubs/{clubId}/practiceMoments/{practiceMomentId}
    - location: string
    - day: timestamp
    - start: string
    - end: string
    - ageGroup: string
    - notes: string

/clubs/{clubId}/members/{uid}
    - ELO: number
    - isActive: boolean
    - joinDate: timestamp
    - role: string
    - capNumber: number
```
## Practice data
### General practice data
```
/clubs/{clubId}/practices/{practiceId}
    - date: timestamp
    - coachId: string

/clubs/{clubId}/practices/{practiceId}/attendance/{uid}
    - state: string
    - timestamp: timestamp
    - history: array
```
### Practice match data
```
/clubs/{clubId}/practices/{practiceId}/games/{gameId}
    - scoreBlack: number
    - scoreWhite: number
    - duration: number

/clubs/{clubId}/practices/{practiceId}/games/{gameId}/teamCompositions/{teamCompositionId}

/clubs/{clubId}/practices/{practiceId}/games/{gameId}/teamCompositions/{teamCompositionId}/players/{uid}
    - position: string

/clubs/{clubId}/practices/{practiceId}/games/{gameId}/gameEvents/{gameEventId}
    - playerId: string
    - team: string
    - type: string
    - timestamp: timestamp
```
### Practice swimming data
```
/clubs/{clubId}/practices/{practiceId}/timings/{timingId}
    - timingType: string
    - timingDate: timestamp
    - distance: number
    - time: number
    - notes: string

/clubs/{clubId}/practices/{practiceId}/timings/{timingId}/results/{resultId}
    - playerId: string
    - result: any
```
## Display data
```
/clubs/{clubId}/displays/{displayDeviceId}
    - content: string
    - contentId: string
    - width: number
    - height: number
    - features: array
    - subscriptionEnd: timestamp

/clubs/{clubId}/displays/{displayDeviceId}/drawings/{drawingId}
    - category: string
    - tags: array
    - title: string
    - timestamp: timestamp
    - userId: string
    - drawingElements: array

/clubs/{clubId}/displays/{displayDeviceId}/images/{imageId}
    - category: string
    - tags: array
    - title: string
    - timestamp: timestamp
    - userId: string
    - url: string
```
## Tournament data
```
/tournaments/{tournamentId}
```
