# Rooms

## Create a Room

Rooms can be created from the app interfaces, or programatically via the API. We currently have no restrictions on the number of rooms you can create within an organization.

### Request
<div class="request">
    <code class="http" title="HTTP">POST /rooms</code>
    <code class="ruby" title="Ruby">Sqwiggle::Room.create</code>
    <code class="js" title="Node.js">client.rooms.create({name: 'Fun Room'}, function(err, resp){});</code>
</div>

### Parameters
<table>
    <tr>
        <td>name</td>
        <td>required</td>
        <td>Display name of the room</td>
    </tr>
</table>


## Retrieve a Room

Retrieves the details of any room that the token has access to. Supply a room ID and Sqwiggle will return 
the corresponding room details.

### Request
<div class="request">
    <code class="http" title="HTTP">GET /rooms/:id</code>
    <code class="ruby" title="Ruby">Sqwiggle::Room.find(id)</code>
    <code class="js" title="Node.js">client.rooms.find(id, function(err, resp){});</code>
</div>


## Update a Room

Updates the specified room by setting the values of the parameters passed. At this time the only parameter
that can be changed is the room name, paths will be automatically generated.

### Request

<div class="request">
    <code class="http" title="HTTP">PUT /rooms/:id</code>
    <code class="ruby" title="Ruby">Sqwiggle::Room.find(id).update(params)</code>
    <code class="js" title="Node.js">client.rooms.update(id, {name: 'More Fun Room'}, function(err, resp){});</code>
</div>

### Parameters

<table>
    <tr>
        <td>id</td>
        <td>required</td>
        <td>ID of the room object to update</td>
    </tr>
    <tr>
        <td>name</td>
        <td>optional</td>
        <td>The rooms display name</td>
    </tr>
</table>


## Remove a Room

Removes the room from the organisation.

### Request 

<div class="request">
    <code class="http" title="HTTP">DELETE /rooms/:id</code>
    <code class="ruby" title="Ruby">Sqwiggle::Room.find(id).delete</code>
    <code class="js" title="Node.js">client.rooms.delete(id, function(err, resp){});</code>
</div>


## List all Rooms

Returns a list of all rooms in the current organization. The rooms are returned in sorted alphabetical order 
by default.

### Request 

<div class="request">
    <code class="http" title="HTTP">GET /rooms</code>
    <code class="ruby" title="Ruby">Sqwiggle::Room.all</code>
    <code class="js" title="Node.js">client.rooms.index({page: 1, limit: 100}, function(err, resp){});</code>
</div>

### Parameters
<table>
    <tr>
        <td>page</td>
        <td>optional</td>
        <td>For paginating through large numbers of rooms, the page of results to retrieve</td>
    </tr>
    <tr>
        <td>limit</td>
        <td>optional</td>
        <td>The number of rooms to return (between 1-100)</td>
    </tr>
</table>
