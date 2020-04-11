<template>
	<div>
		<div id="resume-modal" class="uk-modal-full" uk-modal>
			<div class="uk-modal-dialog">
				<a class="uk-modal-close-full uk-close-large" uk-close></a>
				<div class="uk-modal-body" uk-height-viewport>
					<div class="uk-container resume-container">
						<div class="uk-grid-medium uk-grid-divider" uk-grid>
							<div class="uk-width-1-4@xl uk-width-1-4@l uk-width-1-3@m uk-width-1-1@s">
								<div class="resume-sidebar">
									<div class="resume-ava">
										<img class="uk-border-circle" src="../assets/images/me.jpg" />
									</div>
									<div class="resume-profile">
										<div class="profile-name">{{ fullname }}</div>
										<div class="profile-profession">{{ profession }}</div>
									</div>
									<div class="resume-contact">
										<ul class="uk-nav uk-nav-default">
											<li>
												<a :href="`mailto:${contact.email}`">
													<span class="uk-margin-small-right" uk-icon="icon: mail; ratio: 1.2;"></span>
													{{ contact.email }}
												</a>
											</li>
											<li>
												<a href="#">
													<span class="uk-margin-small-right" uk-icon="icon: location; ratio: 1.2;"></span>
													{{ contact.address }}
												</a>
											</li>
											<li>
												<a :href="contact.twitter.link">
													<span class="uk-margin-small-right" uk-icon="icon: twitter; ratio: 1.2;"></span>
													{{ contact.twitter.id }}
												</a>
											</li>
											<li>
												<a :href="contact.instagram.link">
													<span class="uk-margin-small-right" uk-icon="icon: instagram; ratio: 1.2;"></span>
													{{ contact.instagram.id }}
												</a>
											</li>
											<li>
												<a :href="contact.github.link">
													<span class="uk-margin-small-right" uk-icon="icon: github; ratio: 1.2;"></span>
													{{ contact.github.id }}
												</a>
											</li>
										</ul>
									</div>
								</div>
							</div>
							<div class="uk-width-expand">
								<div class="resume-profile-summary">
									<div class="uk-grid-medium uk-grid-divider uk-child-width-1-1" uk-grid>
										<div>
											<div class="content">
												<div class="heading">Work Experience</div>
												<div v-for="exp in workexperience" :key="exp.position" class="uk-margin-small box">
													<div class="uk-clearfix">
														<div class="title">{{ exp.position }}</div>
														<div class="detail">
															<div class="uk-grid-small" uk-grid>
																<div class="uk-width-1-3@xl uk-width-1-3@l uk-width-1-3@m uk-width-1-1@s">
																	<div class="detail-footer">
																		<span uk-icon="icon: world; ratio: .8"></span>
																		{{ exp.company }}
																	</div>
																</div>
																<div class="uk-width-1-3@xl uk-width-1-3@l uk-width-1-3@m uk-width-1-1@s">
																	<div class="detail-footer">
																		<span uk-icon="icon: location; ratio: .8"></span>
																		{{ exp.location }}
																	</div>
																</div>
																<div class="uk-width-1-3@xl uk-width-1-3@l uk-width-1-3@m uk-width-1-1@s">
																	<div class="detail-footer">
																		<span uk-icon="icon: calendar; ratio: .8"></span>
																		{{ exp.from + ' - ' + exp.to }}
																	</div>
																</div>
															</div>
														</div>
													</div>
												</div>
											</div>
										</div>
										<div>
											<div class="content">
												<div class="heading">Education</div>
											</div>
										</div>
										<div>
											<div class="content">
												<div class="heading">Skills</div>
											</div>
										</div>
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
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
	export default {
		name: 'home',
		data() {
			return {
				fullname: 'Sony Darmawan',
				profession: 'Web Developer',
				contact: {
					email: 'me@sonypiay.com',
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
				workexperience: [
					{
						position: 'ProjectWifi Engineer',
						company: 'Biznet Networks',
						location: 'Jakarta, Indonesia',
						from: 'Desember 2014',
						to: 'June 2019'
					},
					{
						position: 'Jr. Web Developer',
						company: 'Eannovate Creative Technology',
						location: 'Jakarta, Indonesia',
						from: 'Maret 2019',
						to: 'Present'
					}
				],
			}
		}
	}
</script>
