# Quad names
There is a [vendor-agnostic](https://aplwiki.com/wiki/List_of_language_developers) article about [quad-names on the APL Wiki](https://aplwiki.com/wiki/Quad_name). This page focuses on application development with Dyalog.

## System variables

System variables describe the state of the system.  
Some variables are <span class="svstc">static</span> and cannot change.  
Some variables are <span class="svdyn">dynamic</span> and can change without user intervention.  
The others can be <span class="svset">changed by the user</span>.

<style>
	#sysvars {
	}
	.svstc{color: red;}
	.svdyn{color: orange;}
	.svset{color: blue;}
</style>

<table id="sysvars">
	<tr>
		<td class="svstc">⎕A</td>
		<td class="svdyn">⎕DM</td>
		<td class="svdyn">⎕DMX</td>
		<td class="svset">⎕PATH</td>
		<td class="svset">⎕SM</td>
	</tr>
	<tr>
		<td class="svset">⎕TRAP</td>
		<td class="svstc">⎕AN</td>
		<td class="svdyn">⎕EN</td>
		<td class="svset">⎕PP</td>
		<td class="svdyn">⎕STACK</td>
	</tr>
	<tr>
		<td class="svdyn">⎕TS</td>
		<td class="svdyn">⎕AV</td>
		<td class="svset">⎕FR</td>
		<td class="svset">⎕PW</td>
		<td class="svstc">⎕TC</td>
	</tr>
	<tr>
		<td class="svset">⎕USING</td>
		<td class="svset">⎕AVU</td>
		<td class="svset">⎕IO</td>
		<td class="svset">⎕RL</td>
		<td class="svdyn">⎕THIS</td>
	</tr>
	<tr>
		<td class="svdyn">⎕WA</td>
		<td class="svset">⎕CT</td>
		<td class="svdyn">⎕LC</td>
		<td class="svdyn">⎕RSI</td>
		<td class="svdyn">⎕TID</td>
	</tr>
	<tr>
		<td class="svset">⎕WSID</td>
		<td class="svstc">⎕D</td>
		<td class="svset">⎕LX</td>
		<td class="svdyn">⎕RTL</td>
		<td class="svdyn">⎕TNAME</td>
	</tr>
	<tr>
		<td class="svset">⎕WX</td>
		<td class="svset">⎕DCT</td>
		<td class="svset">⎕ML</td>
		<td class="svdyn">⎕SE</td>
		<td class="svdyn">⎕TNUMS</td>
	</tr>
	<tr>
		<td class="svdyn">⎕XSI</td>
		<td class="svset">⎕DIV</td>
		<td class="svstc">⎕NULL</td>
		<td class="svdyn">⎕SI</td>
		<td class="svdyn">⎕TPOOL</td>
	</tr>
</table>