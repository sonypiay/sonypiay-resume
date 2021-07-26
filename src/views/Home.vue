<template>
	<div>

		<!-- start modal resume -->
		<resume-modal :fullname="fullname" :profession="profession" :contact="contact" />
		<!-- end of modal resume -->

		<div class="uk-container uk-margin-large-top">
			<div class="uk-width-3-4@xl uk-width-3-4@l uk-width-2-3@m uk-width-1-1@s uk-align-center">
				<div class="content-profile">
					<div class="uk-grid-large" uk-grid>
						<div class="uk-width-1-4@xl uk-width-1-4@l uk-width-1-4@m uk-width-1-3@s uk-visible@s">
							<img class="ava" src="../assets/images/me.jpg" />
						</div>
						<div class="uk-width-expand">
							<div class="profile-name">{{ fullname }}</div>
							<div class="profile-profession">{{ profession }} Based in Jakarta, Indonesia.</div>

							<div class="profile-content">
								<p>
									I really passionate with web programming, linux, network, learn everything autodidact on the Internet.
									I start code when i was in a high schools.
									I was graduated from Mercubuana University in 2020 as a Bachelor Degree of Information System.
								</p>
								<p>I created several projects such as Company Profile, Inventory &amp; Internal Systems, Hotspot Portal, Mikrotik Controller and more.</p>
								<p>
									Currently work as a Web Developer at <a target="_blank" href="https://www.eannovate.com">Eannovate</a>
								</p>

								<div class="uk-margin-top uk-grid-small uk-child-width-auto" uk-grid>
									<div>
										<strong>
											<a :href="`mailto:${contact.email}`">
												<span uk-icon="icon: mail; ratio: 1"></span>
												Send an Email
											</a>
										</strong>
									</div>
									<div>
										<strong><a uk-toggle="target: #resume-modal" class="btn-resume-modal">Resume</a></strong>
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script type="text/javascript">
	import ResumeModal from '@/components/ResumeModal.vue';

	export default {
		name: 'home',
		components: {
			'resume-modal': ResumeModal,
		},
		data() {
			return {
				fullname: 'Sony Darmawan',
				profession: 'Web Developer',
				contact: {
					email: 'j2megates@gmail.com',
					address: 'Jakarta, Indonesia',
					twitter: {
						link: 'https://twitter.com/sonypiay',
						id: '@sonypiay'
					},
					instagram: {
						link: 'https://instagram.com/sonypiay',
						id: '@sonypiay'
					},
					github: {
						link: 'https://github.com/sonypiay',
						id: 'sonypiay'
					}
				},
			}
		}
	}
</script>
