# Event Channel Set

Quickly create a Event Channel in your ExpressionEngine install with this Channel Set.

The Event Channel Set comes with custom fields and statuses to get you up and running fast. Here’s what’s inside:

### Custom Fields

* `{event_address}`: a Text field for the physical address of the event
* `{event_contact}`: a Grid field to contain contact info for the event
  * `:name` - a Text field for the contact’s name
  * `position` - a Text field for the contact’s position / title
  * `:phone_number` - a Text field for the contact’s phone number
* `{event_description}`: a Textarea to describe the event
* `{event_related_events}`: a Relationship to similar / related events

### Statuses

* Open: published
* Closed: not published
* Featured: to call special attention to an event, typically on the homepage

### Sample Tags

```
{exp:channel:entries channel='event' limit='1' require_entry='yes'}
	{if no_results}
		{redirect='404'}
	{/if}

	<h1>{title}</h1>

	<p>{event_address}</p>

	{event_description}

	<h2>Contact Info</h2>
	<ul>
		{event_contact}
			<li>{event_contact:name}, {event_contact:position}: {event_contact:phone_number}</li>
		{/event_contact}
	</ul>

	{if event_related_events:total_results > 0}
		<h2>See Also</h2>
		<ul>
			{event_related_events}
				<li><a href="{event_related_events:url_title_path='event/index">{event_related_events:title}</a></li>
			{/event_related_events}
		</ul>
	{/if}
{/exp:channel:entries}

```

## License

Copyright (C) 2004 - 2016 EllisLab, Inc.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL ELLISLAB, INC. BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

Except as contained in this notice, the name of EllisLab, Inc. shall not be used in advertising or otherwise to promote the sale, use or other dealings in this Software without prior written authorization from EllisLab, Inc.
