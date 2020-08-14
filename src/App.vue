<template>
  <iowa-bar
    iowa_bar_classes="iowa-bar--narrow"
  ></iowa-bar>

  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="hero-banner"></div>
  </div>
  <hero
    image="src/assets/images/widescreen__2592_x_1458/pano.jpg"
    hero_size="large"
    hero_vertical_alignment="vertical-center"
    hero_horizontal_alignment="horizontal-center"
    hero_classes="bg--black"
    hero_type="image"
    hero_overlay= "gradient-center"
    hero_text=''
    hero_title='<span>Welcome</span> to Iowa'
    hero_title_classes='bold-headline--caps bold-headline bold-headline--negative'
  >
  </hero>

  <div data-uids-cta="data-uids-cta" role="region" class="cta-row__wrapper">
    <div class="cta-row__container">
      <menuGroup
        :items="cta_menu_items"
      ></menuGroup>
    </div>
  </div>

  <verticalDots
    :sections="v_dots_sections"
  >
  </verticalDots>

  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="areas-of-study"></div>
  </div>

 <grid-panel
    link_url= 'https://admissions.uiowa.edu/academics/undergraduate-areas-of-study'
    image= ''
    headline= '200+ Areas<br /> of Study'
    button_text= 'View Areas of Study'
    button_link= 'https://admissions.uiowa.edu/academics/undergraduate-areas-of-study'
    grid_panel_type= 'grid-panel grid-panel--asymmetrical'
    grid_panel_first_column= 'grid-panel__column-content-left grid-panel__content'
    grid_panel_second_column= 'grid-panel__column-image-right'
    grid_content_position= 'first'
    grid_panel_content= '<p>Iowa offers over 200 majors, minors and certificates. Students are encouraged to work across disciplines to find their passion. If you are unsure of what you’d like to study at Iowa, look at an&nbsp;<a href="https://admissions.uiowa.edu/academics/open-major">open major</a>, or take our&nbsp;<a data-cke-saved-href="http://uiowa.mymajors.com/" href="http://uiowa.mymajors.com/">MyMajors assessment</a>&nbsp;to explore possible majors based on your interests and strengths.</p>'
    grid_panel_content_2= ''
    :card_grid = 'true'
    :areas_of_study = 'areas_of_study'
  >
  </grid-panel>

  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="academic-opportunities"></div>
  </div>
  <grid-panel
    link_url= 'https://admissions.uiowa.edu/academics/academics'
    image= 'src/assets/images/viewbook/sections/0315.jpg'
    headline= 'We Work <span>Together</span>'
    button_text= 'View Academic Opportunities'
    button_link= 'https://admissions.uiowa.edu/academics/academics'
    grid_panel_type= 'grid-panel grid-panel--asymmetrical'
    grid_panel_first_column= 'grid-panel__column-image-left'
    grid_panel_second_column= 'grid-panel__column-content-right grid-panel__content'
    grid_content_position= 'second'
    grid_panel_content= '<p>The University of Iowa blends big-school opportunities with close, personal support to help you excel. We remove the barriers between arts and science, between students and faculty—but most of all, between you and anything you’d like to explore.</p>'
    grid_panel_content_2= '<p>How many universities have both a state-of-the-art children’s hospital and a 3,883-pipe Klais organ? Or helped build the Voyager I satellite and the very first creative writing degree program? Just one: Iowa.</p>'
  >
  </grid-panel>

  <div class="stat__wrapper bg--black">
    <template v-for="(stat, index) in stats_1">
      <stat
        :key="index"
        :headline="stat.headline"
        :heading_prefix="stat.heading_prefix"
        :heading_suffix="stat.heading_suffix"
        :stat_description="stat.stat_description"
        :stat_content="stat.stat_content"
      >
      </stat>
    </template>
  </div>

  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="iowa-city"></div>
  </div>
  <Aerial></Aerial>

  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="student-life"></div>
  </div>
  <grid-panel
    link_url= 'https://admissions.uiowa.edu/student-life/student-life'
    image= 'src/assets/images/viewbook/sections/1304.jpg'
    headline= 'MAKE <span>30,000</span> NEW FRIENDS'
    button_text= 'View Student Life'
    button_link= 'https://admissions.uiowa.edu/student-life/student-life'
    grid_panel_type= 'grid-panel grid-panel--asymmetrical'
    grid_panel_first_column= 'grid-panel__column-content-left grid-panel__content'
    grid_panel_second_column= 'grid-panel__column-image-right'
    grid_content_position= 'first'
    grid_panel_content= '<p>Big Ten athletics, theaters, music venues, 500+ student groups, community organizations, student philanthropy, hiking trails, bike paths, workout facilities, hundreds of restaurants and coffee shops and food carts and—you get the idea. There’s a lot to do in Iowa City. Every club, event, and activity is an opportunity to make new connections and find your own close-knit community on campus.</p>'
    grid_panel_content_2= ''
  >
  </grid-panel>

   <div class="stat__wrapper bg--black">
    <template v-for="(stat, index) in stats_2">
      <stat
        :key="index"
        :headline="stat.headline"
        :heading_prefix="stat.heading_prefix"
        :heading_suffix="stat.heading_suffix"
        :stat_description="stat.stat_description"
        :stat_content="stat.stat_content"
      >
      </stat>
    </template>
  </div>

  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="student-outcomes"></div>
  </div>
  <grid-panel
    link_url= 'https://stories.uiowa.edu/student-outcomes'
    image= 'src/assets/images/viewbook/sections/1961.jpg'
    headline= 'Make an <span>Impact</span>'
    button_text= 'View Student Outcomes'
    button_link= 'https://stories.uiowa.edu/student-outcomes'
    grid_panel_type= 'grid-panel grid-panel--asymmetrical'
    grid_panel_first_column= 'grid-panel__column-image-left'
    grid_panel_second_column= 'grid-panel__column-content-right grid-panel__content'
    grid_content_position= 'second'
    grid_panel_content= '<p>Having big ideas isn’t enough—to excel in any career, you need to know how to share them and make them real. Iowa’s leadership in the study and craft of writing helps every Hawkeye learn communication skills that give them an edge. Dedicated career advising, thousands of on-campus job interviews, and countless opportunities for hands-on learning make Iowa grads stand out.</p>'
    grid_panel_content_2= ''
  >
  </grid-panel>

  <div class="stat__wrapper bg--black">
    <template v-for="(stat, index) in stats_3">
      <stat
        :key="index"
        :headline="stat.headline"
        :heading_prefix="stat.heading_prefix"
        :heading_suffix="stat.heading_suffix"
        :stat_description="stat.stat_description"
        :stat_content="stat.stat_content"
      >
      </stat>
    </template>
  </div>


  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="apply"></div>
  </div>
  <div class="grid-panel grid-panel--split">
  <div class="grid-panel__column grid-panel__content">
    <headline
      heading_level= "h2"
      heading_class= "bold-headline--caps bold-headline"
      heading= "How to Apply"
    />
  <hr class="element--spacer-separator" />


<ol class="element--circle-list">
	<li>
		<h3 class="bold-headline bold-headline--serif bold-headline--underline">
			<span class="heading__heading">Complete the required high school courses.</span>
		</h3>


		<p>
			<a href="https://admissions.uiowa.edu/academics-undergraduate-programs-undergraduate/minimum-high-school-course-requirements" class="bttn bttn--secondary bttn--caps">

				View High School Course Requirements
				<i class="fas fa-arrow-right"></i>
			</a>
		</p>

	</li>
	<li>

		<h3 class="bold-headline bold-headline--serif bold-headline--underline">
			<span class="heading__heading">Score 245 or higher on the Regent Admission Index.</span>

		</h3>

		<p>Score 245 or higher on the Regent Admission Index.
			The Regent Admission Index (RAI) is a formula used by all Iowa public universities to make admission a simpler,
			more streamlined process. To calculate your RAI score, use the applicable formula below.
			.</p>

		<p>
			<strong>RAI FORMULA:</strong>
		</p>
		<ul>
			<li>3 x ACT composite score or SAT equivalent</li>
			<li>+ 30 x cumulative GPA</li>
			<li>+ 5 x years of high school core courses complete</li>
		</ul>

		<p>
			<a href="https://admissions.uiowa.edu/rai" class="bttn bttn--secondary bttn--caps">

				Calculate your RAI score
				<i class="fas fa-arrow-right"></i>
			</a>
		</p>

		<p>
			<strong>ACT and SAT Test Scores:</strong>
		</p>
		<p>We understand that COVID-19 has caused limited access to ACT and SAT tests this year. Any academic disruptions you experience will not keep you from becoming a Hawkeye. We encourage you to apply for admission even if you do not have a test score yet. An individual review process may be used to issue provisional admission decisions for students who do not have a test score. Per Iowa Board of Regents policy, a test score will be required at a later time to confirm the admission decision for those students.</p>

		<p>
			<a href="https://admissions.uiowa.edu/testing" class="bttn bttn--secondary bttn--caps">

				View Testing
				<i class="fas fa-arrow-right"></i>
			</a>
		</p>

	</li>

	<li>

		<h3 class="bold-headline bold-headline--serif bold-headline--underline">
			<span class="heading__heading">Meet the admission requirements for your college of choice.</span>

		</h3>

		<p>Admission requirements vary for each college that accepts first-year students.</p>

		<ul>
			<li>College of Liberal Arts and Sciences</li>
			<li>Tippie College of Business
				<em>(direct admission)</em>
			</li>
			<li>College of Education
				<em>(direct admission to the Elementary Teacher Education Program)</em>
			</li>

			<li>College of Engineering
				<em>(direct admission)</em>
			</li>

			<li>College of Nursing
				<em>(direct admission)</em>
			</li>
			<li>College of Pharmacy
				<em>(assured admission)</em>
			</li>

			<li>College of Public Health
				<em>(direct admission)</em>
			</li>
		</ul>

		<p>
			<small>
				<em>Students who do not meet all direct admission requirements for their specific college will be carefully considered on a case-by-case basis. Those who are not directly admitted to their desired college begin school as a CLAS student, applying to
					        their college of choice after completing prerequisite courses and earning a minimum GPA.</em>
			</small>
		</p>
		<p>
			<small>
				<em>Colleges that do not accept first-year students directly include: Dentistry, Law, Pharmacy, Medicine, and the Graduate College.</em>
			</small>
		</p>

		<p>
			<a href="https://admissions.uiowa.edu/academics/first-year-admission" class="bttn bttn--secondary bttn--caps">
				View Requirements
				<i class="fas fa-arrow-right"></i>
			</a>
		</p>

	</li>

</ol>

  </div>

  <div class="grid-panel__column grid-panel__content">


<ol class="element--circle-list counter-increment">
<li>
  <h3 class="bold-headline bold-headline--serif bold-headline--underline">
    <span class="heading__heading">Submit your FAFSA and explore financial aid.</span>
  </h3>
<hr class="element--spacer-separator"/>
  <table class="table is-striped">
    <caption class="element-invisible">Finances</caption>
    <thead>
      <tr>
        <th>Finances</th>
        <th>Cost</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><strong>Iowa residents</strong></td>
        <td>
          <strong>$9,830*</strong>
        </td>
    </tr>
    <tr>
      <td><strong>Nonresidents</strong></td>
      <td>
        <strong>$31,793*</strong>
      </td>
  </tr>
  <tr>
    <td><strong>Standard housing and meal plans</strong></td>
    <td>
      <strong>$11,590 **</strong>
    </td>
  </tr>
</tbody>
</table>

<p>
<small>* Tuition and fees vary by academic program. Tuition and fees listed include a one-time University Records and Documents Fee of $225 for new students.<br/>** Based on a weighted room average and unlimited (Gold) meal plan</small>


</p>

<p>
<a href="http://financialaid.uiowa.edu" class="bttn bttn--secondary bttn--caps">

  Financial Aid
  <i class="fas fa-arrow-right"></i>
</a>
</p>
<p>Submit the
<strong>Free Application for Federal Student Aid (FAFSA)</strong>
early to maximize your available assistance.</p>

<p>
<a href="https://admissions.uiowa.edu/finances/scholarships" class="bttn bttn--secondary bttn--caps">

  Scholarships
  <i class="fas fa-arrow-right"></i>
</a>
</p>
<p>We offer a wide variety of scholarships and grants.</p>

</li>

<li>

<h3 class="bold-headline bold-headline--serif bold-headline--underline">
<span class="heading__heading">Apply for housing and dining.</span>
</h3>

<p>Access the housing application through your admissions profile on
<a data-cke-saved-href="https://myui.uiowa.edu" href="https://myui.uiowa.edu">myui.uiowa.edu</a>
and pay the nonrefundable $75 housing application fee.
<br></p>
<p>We have a number of housing options available to suit your ideal student experience. We strongly recommend applying for housing early. Assignments are made on a first-come, first-served basis. Apply by May 3, 2021 for the opportunity to request a roommate and select your room.</p>

<p>
<a href="http://housing.uiowa.edu" class="bttn bttn--secondary bttn--caps">

  Housing Information
  <i class="fas fa-arrow-right"></i>
</a>
</p>

<p>
<a href="http://dining.uiowa.edu" class="bttn bttn--secondary bttn--caps">
  Dining Information
  <i class="fas fa-arrow-right"></i>
</a>
</p>

</li>

</ol>

  </div>
  </div>

  <main></main>

  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="to-be-a-hawkeye"></div>
  </div>
  <div class="image-grid">
  <div class="image-grid__section">

  <img class="card__img" src="src/assets/images/viewbook/sections/0849.jpg" alt="Alt Text">
  </div>

  <div class="image-grid__section">

  <img class="card__img" src="src/assets/images/viewbook/sections/dorm.jpg" alt="Alt Text">
  </div>


  <div class="image-grid__section">

  <img class="card__img" src="src/assets/images/viewbook/sections/0297-Pano5.jpg" alt="Alt Text">
  </div>


  <div class="image-grid__section grid__content bg-pattern--brain-reversed">
    <headline
      heading_level= "h2"
      heading_class= "bold-headline--caps bold-headline"
      heading= "Its <span>Great</span> to<br /> be a Hawkeye"
    />
  </div>


  <div class="image-grid__section">

    <img class="card__img" src="src/assets/images/viewbook/sections/1152.jpg" alt="Alt Text">
    </div>


  <div class="image-grid__section">

  <img class="card__img" src="src/assets/images/viewbook/sections/0027.jpg" alt="Alt Text">
  </div>


  </div>

  <footerSection
    :contact_info="contact_info"
    :social_media_links="social_media_links"
  ></footerSection>

</template>

<script>
import Hero from './components/Hero.vue';
import Stat from './components/Stat.vue';
import IowaBar from './components/IowaBar.vue';
import GridPanel from './components/GridPanel.vue';
import headline from './components/headline.vue';
import verticalDots from './components/verticalDots.vue';
import uidsButton from './components/uidsButton.vue';
import Aerial from './components/Aerial.vue';
import menuGroup from './components/menuGroup.vue';
import footerSection from './components/footerSection.vue';

export default {
  name: 'App',
  components: {
    Hero,
    Stat,
    IowaBar,
    headline,
    verticalDots,
    GridPanel,
    uidsButton,
    Aerial,
    menuGroup,
    footerSection
  },
  data() {
    return {
      areas_of_study: [
        {
          headline: 'Business, Economics, and Management',
          image: 'src/assets/images/viewbook/areas/1.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/biz-econ-mgmt',
        },
        {
          headline: 'Education',
          image: 'src/assets/images/viewbook/areas/2.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/edu',
        },
        {
          headline: 'Engineering and Computing',
          image: 'src/assets/images/viewbook/areas/3.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/engr-comp',
        },
        {
          headline: 'Health Sciences',
          image: 'src/assets/images/viewbook/areas/4.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/health-sci',
        },
        {
          headline: 'Languages, culture, and society',
          image: 'src/assets/images/viewbook/areas/5.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/lang-cult-soc',
        },
        {
          headline: 'Life and natural sciences',
          image: 'src/assets/images/viewbook/areas/6.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/life-nat-sci',
        },
        {
          headline: 'Math and quantitative sciences',
          image: 'src/assets/images/viewbook/areas/7.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/math-quant-sci',
        },
        {
          headline: 'Preprofessional programs',
          image: 'src/assets/images/viewbook/areas/8.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/preprofessional',
        },
        {
          headline: 'Social sciences and policy',
          image: 'src/assets/images/viewbook/areas/9.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/soc-sci-pol',
        },
        {
          headline: 'Visual and performing arts',
          image: 'src/assets/images/viewbook/areas/10.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/vis-perf-arts',
        },
        {
          headline: 'Writing, communications, literature, and media',
          image: 'src/assets/images/viewbook/areas/11.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/write-comm-media',
        },
        {
          headline: '',
          image: '',
          button_text: 'Browse by Major',
          button_link: 'https://admissions.uiowa.edu/academics/undergraduate-areas-of-study',
        }
      ],
      stats_1: [
        {
          headline: '34',
          heading_prefix: '#',
          heading_suffix: '',
          stat_description: 'BEST PUBLIC UNIVERSITY BY U.S. NEWS & WORLD REPORT',
          stat_content: 'Among the top 2% of universities worldwide.',
        },
        {
          headline: '15:1',
          heading_prefix: '',
          heading_suffix: '',
          stat_description: 'STUDENT-TO-FACULTY RATIO',
          stat_content: 'Get to know your professors.',
        },
        {
          headline: '23',
          heading_prefix: '',
          heading_suffix: '',
          stat_description: 'INTERNATIONAL FULBRIGHT SCHOLARS IN 2020',
          stat_content: 'That’s the same as some Ivy League schools.',
        },
        {
          headline: '1 in 3',
          heading_prefix: '',
          heading_suffix: '',
          stat_description: 'UNDERGRADS PARTICIPATE IN RESEARCH',
          stat_content: 'Gain experience now.',
        }
      ],
      stats_2: [
        {
          headline: '500',
          heading_prefix: '',
          heading_suffix: '',
          stat_description: 'STUDENT<br />  ORGANIZATIONS',
          stat_content: 'Or, start your own.',
        },
         {
          headline: '100',
          heading_prefix: '',
          heading_suffix: '',
          stat_description: 'RESTAURANTS AND<br />  CAFÉS',
          stat_content: 'From vegan brunch to pie shakes.',
        },
         {
          headline: '400',
          heading_prefix: '',
          heading_suffix: '',
          stat_description: 'ARTS PERFORMANCES Available EACH YEAR',
          stat_content: 'For $5 or less.',
        },
        {
          headline: '24',
          heading_prefix: '',
          heading_suffix: '',
          stat_description: 'NCAA DIVISION I<br />  TEAMS',
          stat_content: 'There’s nothing like a Hawkeye game.',
        }
      ],
      stats_3: [
        {
          headline: '95',
          heading_prefix: '',
          heading_suffix: '',
          stat_description: 'OVERALL JOB/GRADUATE SCHOOL PLACEMENT RATE',
          stat_content: 'Business <strong>97%</strong><br />Education <strong>91%</strong><br />Engineering  <strong>96%</strong><br /> Liberal Arts and Sciences <strong>94%</strong><br /> Nursing <strong>99%</strong><br />Pharmacy <strong>97%</strong>',
        },
         {
          headline: '4,000',
          heading_prefix: '',
          heading_suffix: '',
          stat_description: 'STUDENT<br />  INTERNSHIPS',
          stat_content: 'Everywhere from NASA to the Minnesota Vikings.',
        },
         {
          headline: '4,100',
          heading_prefix: '',
          heading_suffix: '',
          stat_description: 'Employers have hired Iowa Graduates the past three years',
          stat_content: 'Gain real-world skills that make résumés stand out.',
        },
        {
          headline: '1,316',
          heading_prefix: '',
          heading_suffix: '',
          stat_description: 'STUDENTS STUDIED ABROAD LAST YEAR',
          stat_content: 'Spanning the globe in 69 countries.',
        }
      ],
      cta_menu_items: [
        {
          text: 'Apply Now',
          url: 'https://admissions.uiowa.edu/apply/first-year-student-application-process',
          item_class: 'bttn bttn--outline bttn--tertiary bttn--transparent bttn--caps bttn--apply'
        },
        {
          text:  'Schedule a Visit',
          url: 'https://admissions.uiowa.edu/visit-campus',
          item_class: 'bttn bttn--outline bttn--tertiary bttn--transparent bttn--caps bttn--visit'
        },
        {
          text: 'Contact Us',
          url: 'https://admissions.uiowa.edu/contact-us',
          item_class: 'bttn bttn--outline bttn--tertiary bttn--transparent bttn--caps bttn--ask'
        },
        {
          text: 'Request Information',
          url: 'https://www.maui.uiowa.edu/maui/pub/admissions/webinquiry/undergraduate.page',
          item_class: 'bttn bttn--outline bttn--tertiary bttn--transparent bttn--caps bttn--connect'
        },
      ],
      v_dots_sections: [
        {
          section_title: 'Back to Top',
          section_id: 'hero-banner'
        },
        {
          section_title: 'Areas of Study',
          section_id: 'areas-of-study'
        },
        {
          section_title: 'Acdemic Opportunities',
          section_id: 'academic-opportunities'
        },
        {
          section_title: 'Iowa City',
          section_id: 'iowa-city'
        },
        {
          section_title: 'Student Life',
          section_id: 'student-life'
        },
        {
          section_title: 'Student Outcomes',
          section_id: 'student-outcomes'
        },
        {
          section_title: 'How to Apply',
          section_id: 'apply'
        },
      ],
      contact_info: '<p>Iowa City, Iowa 52242<br><a href="tel:319-335-3847"><i class="fas fa-phone"></i> 319-335-3847</a><br /></p>',
      social_media_links: [
        {
          text: 'Facebook',
          url: 'http://www.facebook.com/admissions.office',
          icon_class: 'fab fa-facebook-square'
        },
        {
          text: 'Instagram',
          url: 'http://instagram.com/iowaadmissions',
          icon_class: 'fab fa-instagram'
        },
        {
          text:  'Twitter',
          url: 'https://twitter.com/iowaadmissions',
          icon_class: 'fab fa-twitter-square'
        },
        {
          text: 'Youtube',
          url: 'http://www.youtube.com/uiowaadmissions',
          icon_class: 'fab fa-youtube'
        }
      ]
    }
  },
  created() {
    document.querySelector('body').classList.add('header-sticky');
  }
}
</script>

<style lang="scss">
  $imgpath: '../node_modules/@uiowa/uids/src/assets/images';
  @import '../node_modules/@uiowa/uids/src/components/typography/lists/lists.scss';
  @import '../node_modules/@uiowa/uids/src/components/tables/tables.scss';
  @import '../node_modules/@uiowa/uids/src/components/typography/paragraph/paragraph.scss';
  @import '../node_modules/@uiowa/uids/src/components/colors/colors.scss';
  @import '../node_modules/@uiowa/uids/src/components/grid-panel/grid-panel.scss';
  @import '../node_modules/@uiowa/uids/src/components/card/card.scss';
  @import '../node_modules/@uiowa/uids/src/components/layouts/viewbook/viewbook.scss';
</style>
