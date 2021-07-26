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

										<!-- work experience -->
										<div>
											<div class="content">
												<div class="heading">Work Experience</div>
												<div v-for="exp in workexperience" :key="exp.position" class="uk-margin-small box">
													<div class="uk-clearfix">
														<div class="title">{{ exp.position }}</div>
														<div class="detail">
															<div class="uk-grid-small" uk-grid>
																<div class="uk-width-1-3@m">
																	<div class="detail-footer">
																		<span uk-icon="icon: world; ratio: .8"></span>
																		{{ exp.company }}
																	</div>
																</div>
																<div class="uk-width-1-3@m">
																	<div class="detail-footer">
																		<span uk-icon="icon: location; ratio: .8"></span>
																		{{ exp.location }}
																	</div>
																</div>
																<div class="uk-width-1-3@m">
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
										<!-- work experience -->

										<!-- education -->
										<div>
											<div class="content">
												<div class="heading">Education</div>
												<div v-for="(ed, index) in education" :key="`education-${index}`" class="uk-margin-small box">
													<div class="uk-clearfix">
														<div class="title">{{ ed.name }}</div>
														<div class="detail">
															<div class="uk-grid-small" uk-grid>
																<div class="uk-width-1-2@s">
																	<div class="detail-footer">
																		<span uk-icon="icon: location; ratio: .8"></span>
																		{{ ed.jurusan }}
																	</div>
																</div>
																<div class="uk-width-1-2@s">
																	<div class="detail-footer">
																		<span uk-icon="icon: calendar; ratio: .8"></span>
																		{{ ed.since }}
																	</div>
																</div>
															</div>
														</div>
													</div>
												</div>
											</div>
										</div>
										<!-- education -->

										<!-- skills -->
										<div>
											<div class="content">
												<div class="heading">Skills</div>
                        <div class="uk-margin-small box">
                          <div class="uk-grid-small" uk-grid>
                            <div v-for="(sk, index) in skills" :key="`skills-${index}`" class="uk-width-1-3@s">
                              <div class="detail">
                                <div class="detail-footer">
                                  <span uk-icon="icon: hashtag; ratio: .8"></span>
                                  <span v-html="sk"></span>
                                </div>
                              </div>
                            </div>
                          </div>
                        </div>
											</div>
										</div>
										<!-- skills -->

                    <!-- portfolio -->
                    <div>
                      <div class="content">
                        <div class="heading">My Works</div>
                        <div v-for="(item, index) in myworks" :key="`myworks-${index}`" class="uk-margin-small box">
                          <div class="title">{{ item.project_name }}</div>
                          <div class="detail">
                            <div v-show="item.description" class="detail-footer">
                              Description: <div v-html="item.description"></div>
                            </div>

                            <!-- <div class="uk-grid-small" v-if="item.images.length > 0" uk-grid>
                              <div class="uk-width-1-3@s" v-for="(img, index_img) in item.images" :key="`img-portfolio-${item.project_name}-${index_img}`">
                                <img :src="img" alt="portfolio" class="uk-width-1-1" />
                              </div>
                            </div> -->
                          </div>
                        </div>
                      </div>
                    </div>
                    <!-- portfolio -->

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

<script>
export default {
  name: 'resume-modal-component',
  props: [
    'fullname',
    'profession',
    'contact'
  ],
  data() {
    return {
      workexperience: [
        {
          position: 'ProjectWifi Engineer',
          company: 'PT. Supra Primatama Nusantara',
          location: 'Jakarta, Indonesia',
          from: 'Desember 2014',
          to: 'June 2019'
        },
        {
          position: 'Web Developer',
          company: 'PT. Eannovate Creative Technology',
          location: 'Jakarta, Indonesia',
          from: 'Maret 2020',
          to: 'Now'
        }
      ],
      education: [
        {
          name: 'SMK Negeri 1 Jakarta',
          since: 'Jun 2010 - Mei 2014',
          jurusan: 'Computer and Network Engineering'
        },
        {
          name: 'Mercu Buana University',
          since: 'Sep 2015 - Jan 2020',
          jurusan: 'Information System'
        },
      ],
      skills: [
        "PHP, Laravel",
        "HTML &amp; CSS",
        "Javascript",
        "MySQL, SQL Server",
        "Sass",
        "Vue JS",
        "Linux (CentOS, Debian, Ubuntu)",
        "Mikrotik Router",
        "Git",
        "Restful API"
      ],
      myworks: [
        {
          project_name: 'ProjectWifi Management Tools',
          description: 'Sistem informasi divisi ProjectWifi untuk request kebutuhan access point dan approval. Selain itu inventori data untuk pendataan model access point, ip, coordinate dan lokasi yang terpasang.',
          images: [
            '../assets/images/portfolio/pmtools.jfif'
          ]
        },
        {
          project_name: 'APEL Subdit Harda Polda Metro Jaya',
          description: 'Aplikasi penyelidikan terintegrasi elektronik Polda Metro Jaya (APEL)',
          images: [
            '../assets/images/portfolio/biznetwifi-landing-page.png'
          ]
        },
        {
          project_name: 'BiznetWifi Landing Page',
          description: 'Portal Biznetwifi dengan design baru.',
          images: [
            '../assets/images/portfolio/pmtools/portfolio1.jpg'
          ]
        },
        {
          project_name: 'Online Digital Wedding',
          description: 'Undangan pernikahan berbasis digital (website).',
          images: [
            '../assets/images/portfolio/online_wedding.PNG',
            '../assets/images/portfolio/online_wedding.PNG',
            '../assets/images/portfolio/online_wedding.PNG',
            '../assets/images/portfolio/online_wedding.PNG'
          ]
        },
        {
          project_name: 'Solusi Pajakku',
          description: 'Platform penjadwalan untuk konsultasi pajak.',
          images: [
            '../assets/images/portfolio/pmtools.jfif'
          ]
        },
        {
          project_name: 'Labmode Indonesia',
          description: 'Platform Riset, Direktori, Jobs dan Berita Seputar Industri Fashion.',
          images: [
            '../assets/images/portfolio/pmtools.jfif'
          ]
        },
        {
          project_name: 'Garden Buana',
          description: 'Platform penyedia jasa yang mempertemukan tukang kebun dengan pelanggan.',
          images: [
            '../assets/images/portfolio/pmtools.jfif'
          ]
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
</style>
