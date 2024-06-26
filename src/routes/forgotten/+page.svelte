<!-- src/routes/+page.svelte -->
<script lang="ts">
	import { Auth } from '@supabase/auth-ui-svelte'
	import { ThemeSupa } from '@supabase/auth-ui-shared'
	import * as zh from '../../lib/auth-zh.json'

	export let data
</script>

<svelte:head>
	<title>首页 - 忘记密码</title>
</svelte:head>

<div class="row flex-center flex">
	<div class="col-6 form-widget">
		<Auth
			supabaseClient={data.supabase}
			view="forgotten_password"
			redirectTo={`${data.url}/auth/callback`}
			localization={{ variables: zh }}
			showLinks={false}
			appearance={{ theme: ThemeSupa, style: { input: 'color: #fff' } }}
		/>
	</div>
</div>