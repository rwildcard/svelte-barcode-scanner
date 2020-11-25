<script>
	import {
	  Grid,
	  Row,
	  Column,
	  Select,
	  SelectItem,
		Button,	
		
	} from "carbon-components-svelte";
	import { getContext } from "svelte";
	import Close32 from "carbon-icons-svelte/lib/Close32";
	const { carbon_theme } = getContext("Theme");
	let theme_selected = true;
  </script>
  
  <Row>
	<Column lg="{16}">
	  <h1 style="margin-bottom: 1.5rem">Svelte Barcode Scanner</h1>
	</Column>
  </Row>
  
  <Row>
	<Column>

		<Grid condensed>
		
			<Row >
			{#if !theme_selected}
				<Column  noGutter >
					<Select inline 
						labelText="Color Theme"
						bind:selected="{$carbon_theme}"
						
					
					>
						<SelectItem value="white" text="White" />
						<SelectItem value="g10" text="Gray 10" />
						<SelectItem value="g90" text="Gray 90" />
						<SelectItem value="g100" text="Gray 100" />
					</Select>
					
				</Column>
				<Column>
					<Button 
						icon={Close32}
						hasIconOnly
						tooltipPosition="bottom"
						tooltipAlignment="center"
						iconDescription="Close Selection"
						size='small'
						on:click={() => theme_selected = true}
					/>
				</Column>
			{:else}
				<Button on:click="{() => theme_selected = false}" style="margin-bottom: 1rem">Select Theme</Button>
			{/if}
			</Row>
			<Row>
			<h4>
				This barcode scanner should be able to read from a devices camera and scan the barcodes that are focused on.
			</h4>
			</Row>
	
		
		</Grid>

	</Column>
  </Row>