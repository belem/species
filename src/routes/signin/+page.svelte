<!-- src/routes/+page.svelte -->
<script lang="ts">
	import { Auth } from '@supabase/auth-ui-svelte'
	import { ThemeSupa } from '@supabase/auth-ui-shared'
    import * as zh from '../../lib/auth-zh.json'

	export let data
</script>

<svelte:head>
	<title>首页 - 登录</title>
</svelte:head>

<div class="row flex-center flex">
	<div class="col-6 form-widget">
		<Auth
			supabaseClient={data.supabase}
			providers={['google', 'github', 'twitter']}
			view="sign_in"
            localization={{ variables: zh }}
			redirectTo={`${data.url}/auth/callback`}
			showLinks={false}
			appearance={{ theme: ThemeSupa, style: { input: 'color: #fff' } }}
		/>
	</div>
</div>

<div class="row flex-center flex">
	<div class="col-6 form-widget">
		<a href="/signup">注册新用户</a> <a href="/forgotten">忘记密码</a>
	</div>
</div>