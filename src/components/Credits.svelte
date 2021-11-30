<script>
	export let data;
	let teams = [];
	for (const property in data) {
		let members = [];
		for (const element of data[property]) {
			members.push(element);
		}
		teams.push({ team_name: property, members: members });
	}
</script>

{#each teams as team}
	<h3>{team.team_name}</h3>
	<p>
		{#each team.members as member, index}
			{#if index !== team.members.length - 1}
				<a href={member.link} target="_blank">{member.name},</a>
			{:else}
				<a href={member.link} target="_blank">{member.name}</a>
			{/if}
		{/each}
	</p>
{/each}

<style>
	a {
		padding-right: 0.25rem;
	}
</style>
