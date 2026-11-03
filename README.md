# Property MCP server: Singapore new launches

An MCP server for Singapore new-launch condominiums. Your assistant can search the floor plans and area details Daniel Koh has reviewed from developer materials and quote the buyer rules that apply.

For now your assistant answers your questions and Daniel takes calls by WhatsApp: message him there to talk a shortlist through. Booking a call through your assistant is not open yet.

This is a trial. Free to the buyer on new launches.

> Trial service: this lists a selection of Singapore new launches, not every project on the market. A launch that is not here may still be available; ask the agent.

> Prices are guidance from developer price lists: indicative before launch, reset on booking day, and subject to promotions afterwards. Treat them as a starting point and confirm with the agent.

## Connect

Server address: https://property.bluebed.ai/mcp (Streamable HTTP, no sign-in).

- **Claude.** Open Settings, then Connectors, choose Add custom connector, and paste https://property.bluebed.ai/mcp.
- **Claude Code.** Run: claude mcp add --transport http property https://property.bluebed.ai/mcp
- **ChatGPT.** Where your plan supports custom connectors, turn on developer mode and add a custom connector with the same address, https://property.bluebed.ai/mcp.
- **Cursor.** Add the address https://property.bluebed.ai/mcp as a url entry under mcpServers in ~/.cursor/mcp.json.

## Tools

| Tool | What it does |
| --- | --- |
| `list_launches` | Lists the new launches this service covers: name, property type (condo or ec, an executive condominium), district, street, number of units, stage, launch date, whether it is sold out, and whether floor plans and area details are available. It covers a selection of launches during the trial. Every answer carries its source, the date it was reviewed, the stage of the launch, and the agent's licence details. Anything the developer material does not settle is returned as a gap with the question to ask, never as a guess. |
| `search_floor_plans` | Searches floor plans across the reviewed launches, a selection during the trial. Filter by property type (condo or ec), bedrooms, size in square feet, postal district, launch stage, features such as a kitchen window, and a maximum budget in Singapore dollars. Plans in matches meet every constraint you supplied; plans in close miss exactly one, or could not be checked on one, as shown in each plan's fit (met, missed or unknown). The close list holds at most 20 plans, those with the fewest unknowns first; close_total says how many came close and close_truncated whether some were left out, so narrow the filters to see them. Cull both lists against what your user actually wants. Each result gives the plan, its stacks (stacks_note explains an asterisk), a link to the plan image, and a price with its kind and date. When nothing matches or comes close, the reply names which filters excluded the plans. Prices are guidance from developer price lists: indicative before launch, reset on booking day, and subject to promotions afterwards. Treat them as a starting point and confirm with the agent. Every answer carries its source, the date it was reviewed, the stage of the launch, and the agent's licence details. Anything the developer material does not settle is returned as a gap with the question to ask, never as a guess. |
| `get_launch` | Returns one launch by slug: its property type (condo or ec, which adds a notice on executive condominiums), its reviewed facts with source and page, the price statement with its kind and date, and the gaps the material leaves open. Prices are guidance from developer price lists: indicative before launch, reset on booking day, and subject to promotions afterwards. Treat them as a starting point and confirm with the agent. Every answer carries its source, the date it was reviewed, the stage of the launch, and the agent's licence details. Anything the developer material does not settle is returned as a gap with the question to ask, never as a guess. |
| `get_unit_type` | Returns one unit type of a launch by slug and type name: size, bathrooms, powder rooms and WCs, stacks (stacks_note explains an asterisk), the plan image, the answers read from the plan, and the questions the plan does not settle. Prices are guidance from developer price lists: indicative before launch, reset on booking day, and subject to promotions afterwards. Treat them as a starting point and confirm with the agent. Every answer carries its source, the date it was reviewed, the stage of the launch, and the agent's licence details. Anything the developer material does not settle is returned as a gap with the question to ask, never as a guess. |
| `get_area` | Returns the reviewed area details of a launch by slug: address, tenure, nearby amenities with straight-line distances, schools within two kilometres, and food places the agent has visited himself. Schools are listed for orientation only and the reply says where to verify them. Available for launches that show area details in list_launches, even when floor plans are not yet available. Every answer carries its source, the date it was reviewed, the stage of the launch, and the agent's licence details. Anything the developer material does not settle is returned as a gap with the question to ask, never as a guess. |
| `rules_for_buyer` | Quotes the Singapore property rules that apply to a buyer, exactly as published, with the authority, source link, effective date and the date each was last checked: additional buyer's stamp duty, buyer's stamp duty, financing limits and seller's stamp duty. It quotes and does not work out any duty or rate; read the figure from the quote. Seller's stamp duty depends on the purchase date, so supply purchase_date to get the right regime. Supply slug for an executive condominium launch to add the EC rules that apply to its site. A rule that is being re-checked is named without its quote. This is general information and not advice on a particular purchase; confirm with the agent. |
| `book_call` | Booking a call through your assistant is not open yet. Calling this holds nothing and takes no details: it returns a WhatsApp link to the agent, with a short neutral message already written, and the address of the contact page. Show your user the link if they want to talk to the agent. |
| `confirm_booking` | Booking a call through your assistant is not open yet. Calling this holds nothing and takes no details: it returns a WhatsApp link to the agent, with a short neutral message already written, and the address of the contact page. Show your user the link if they want to talk to the agent. |
| `check_booking` | Booking a call through your assistant is not open yet. Calling this holds nothing and takes no details: it returns a WhatsApp link to the agent, with a short neutral message already written, and the address of the contact page. Show your user the link if they want to talk to the agent. |
| `cancel_booking` | Booking a call through your assistant is not open yet. Calling this holds nothing and takes no details: it returns a WhatsApp link to the agent, with a short neutral message already written, and the address of the contact page. Show your user the link if they want to talk to the agent. |
| `about` | Says who runs this service, the agent's CEA registration and agency licence, how the service is paid for, and how to reach the agent. |

## Who runs this

Daniel Koh, CEA registration R073362I, ERA Realty Network Pte Ltd, licence L3002382K.

More at https://property.bluebed.ai/connect

---

Generated from the server's tool list; do not edit by hand.
