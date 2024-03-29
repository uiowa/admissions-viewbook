<template>
  <iowa-bar
    iowa_bar_classes="iowa-bar--narrow"
  />

  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="hero-banner"></div>
  </div>
  <banner
    image="./images/widescreen__2592_x_1458/pano.jpg"
    banner_size="large"
    banner_vertical_alignment="vertical-center"
    banner_horizontal_alignment="horizontal-center"
    banner_type="image"
    banner_overlay= "gradient-center"
    banner_title="<span>Welcome</span> to Iowa"
    banner_title_classes="headline headline--uppercase"
  />

  <div data-uids-cta="data-uids-cta" role="region" class="cta-row__wrapper">
    <div class="cta-row__container">
      <menuGroup
        :items="cta_menu_items"
      />
    </div>
  </div>

  <verticalDots
    :sections="v_dots_sections"
  />

  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="areas-of-study"></div>
  </div>

  <grid-panel
    link_url= "https://admissions.uiowa.edu/academics/undergraduate-areas-of-study"
    image= ""
    headline= "200+ Areas<br /> of Study"
    button_text= "View Areas of Study"
    button_link= "https://admissions.uiowa.edu/academics/undergraduate-areas-of-study"
    grid_panel_type= "grid-panel grid-panel--asymmetrical"
    grid_panel_first_column= "grid-panel__column-content-left grid-panel__content"
    grid_panel_second_column= "grid-panel__column-image-right"
    grid_content_position= "first"
    grid_panel_content= '<p>Iowa offers over 200 majors, minors and certificates. You’re free to mix and match majors, work across different fields, and add areas of focus as you go. If you are unsure of what you’d like to study at Iowa, look at an&nbsp;<a href="https://admissions.uiowa.edu/academics/open-major">open major</a>, or take our&nbsp;<a data-cke-saved-href="http://uiowa.mymajors.com/" href="http://uiowa.mymajors.com/">MyMajors assessment</a>&nbsp;to explore possible majors based on your interests and strengths.</p>'
    grid_panel_content_2= ""
    :card_grid = "true"
    :areas_of_study = "areas_of_study"
  />

  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="academic-opportunities"></div>
  </div>
  <grid-panel
    link_url= "https://admissions.uiowa.edu/academics/academics"
    image= "/images/viewbook/sections/0315.jpg"
    headline= "A Campus <span>Without</span><span>Limits</span>"
    button_text= "View Academic Opportunities"
    button_link= "https://admissions.uiowa.edu/academics/academics"
    grid_panel_type= "grid-panel grid-panel--asymmetrical"
    grid_panel_first_column= "grid-panel__column-image-left"
    grid_panel_second_column= "grid-panel__column-content-right grid-panel__content"
    grid_content_position= "second"
    grid_panel_content= "<p>We believe in breaking barriers and providing a limitless environment. That’s why Hawkeyes excel in everything they do.</p>"
    grid_panel_content_2= "<p>From the most prestigious creative writing program in the country to a nationally recognized teaching hospital, the University of Iowa is where you’ll find exciting, real-world experiences. With small class sizes and access to one-on-one mentoring opportunities, you’ll receive the academic support you deserve.</p>"
  />

  <div class="stat__wrapper bg--black">
    <template v-for="(stat, index) in stats_1" :key="index">
      <stat
        :headline="stat.headline"
        :headline_prefix="stat.headline_prefix"
        :headline_suffix="stat.headline_suffix"
        :stat_description="stat.stat_description"
        :stat_content="stat.stat_content"
      />
    </template>
  </div>

  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="iowa-city"></div>
  </div>
  <Aerial />

  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="student-life"></div>
  </div>
  <grid-panel
    link_url= "https://admissions.uiowa.edu/student-life/student-life"
    image= "/images/viewbook/sections/HerkySurfing.jpg"
    headline= "It’s Great to Be a <span>Hawkeye</span>"
    button_text= "View Student Life"
    button_link= "https://admissions.uiowa.edu/student-life/student-life"
    grid_panel_type= "grid-panel grid-panel--asymmetrical"
    grid_panel_first_column= "grid-panel__column-content-left grid-panel__content"
    grid_panel_second_column= "grid-panel__column-image-right"
    grid_content_position= "first"
    grid_panel_content= "<p>Iowa is friendly and inclusive—a place where you can be yourself, try new things, and have fun in one of America’s top college towns. You’ll find that every club, event, and activity is an opportunity to meet new people and build your own close-knit community. We welcome students from all backgrounds through our on-campus multicultural centers and events held year-round that celebrate diversity.</p>"
    grid_panel_content_2= ""
  />

  <div class="stat__wrapper bg--black">
    <template v-for="(stat, index) in stats_2" :key="index">
      <stat
        :headline="stat.headline"
        :headline_prefix="stat.headline_prefix"
        :headline_suffix="stat.headline_suffix"
        :stat_description="stat.stat_description"
        :stat_content="stat.stat_content"
      />
    </template>
  </div>

  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="student-outcomes"></div>
  </div>
  <grid-panel
    link_url="https://stories.uiowa.edu/student-outcomes"
    image="/images/viewbook/sections/2023_05_03-Cap and Gown Pentacrest Commercial Shoot jatorner -0350.JPG"
    headline="Hawkeyes Get <span>Hired</span>"
    button_text="View Student Outcomes"
    button_link="https://stories.uiowa.edu/student-outcomes"
    grid_panel_type="grid-panel grid-panel--asymmetrical"
    grid_panel_first_column="grid-panel__column-image-left"
    grid_panel_second_column="grid-panel__column-content-right grid-panel__content"
    grid_content_position="second"
    grid_panel_content='<p>With platforms to share your ideas, hands-on learning opportunities, dedicated career advising, and valued internships in your field, Iowa provides the experiences you need to stand out in a competitive workforce. You’ll make connections and get support from a network of nearly 300,000 alumni. That’s why, as a Hawkeye, you’ll get hired.</p>'
    grid_panel_content_2= ""
  />

  <div class="stat__wrapper bg--black">
    <template v-for="(stat, index) in stats_3" :key="index">
      <stat
        :headline="stat.headline"
        :headline_prefix="stat.headline_prefix"
        :headline_suffix="stat.headline_suffix"
        :stat_description="stat.stat_description"
        :stat_content="stat.stat_content"
      />
    </template>
  </div>


  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="apply"></div>
  </div>
  <div class="grid-panel grid-panel--split">
    <div class="grid-panel__column grid-panel__content">
      <headline
        headline_level="h2"
        headline_class="bold-headline--caps bold-headline"
        headline="How to Apply"
      />
      <hr class="element--spacer-separator" />
      <ol class="element--circle-list">
        <li>
          <h3 class="bold-headline bold-headline--serif bold-headline--underline">
            <span class="headline__heading">Complete the required high school courses.</span>
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
            <span class="headline__heading">Your Regent Admission Index Score.</span>
          </h3>

          <p>Score 245 or higher (residents), 255 or higher (nonresidents) on the Regent Admission Index. The Regent Admission Index (RAI) is a formula used by all Iowa public universities to make admission a simpler, more streamlined process. To calculate your RAI score, use the applicable formula below.
          </p>

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

          <p><strong>ACT and SAT Test Scores:</strong></p>
          <p>The Iowa Board of Regents has permanently extended a provision that gives students the option to include or not include their test scores when applying to Iowa’s public universities. Students who wish to be considered for admission without a test score may leave the test score section blank on the application. An individual review process will be used to make an admission decision for students who do not self-report a test score as part of their application. Students admitted to the University of Iowa without test scores may also be considered for direct admission to University of Iowa academic programs and some merit scholarships awarded by the Office of Admissions.</p>

          <p>
            <a href="https://admissions.uiowa.edu/testing" class="bttn bttn--secondary bttn--caps">
              View Testing
              <i class="fas fa-arrow-right"></i>
            </a>
          </p>

        </li>

        <li>
          <h3 class="bold-headline bold-headline--serif bold-headline--underline">
            <span class="headline__heading">Meet the admission requirements for your college of choice.</span>
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
            <span class="headline__heading">Submit your FAFSA and explore financial aid.</span>
          </h3>

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
                <strong>$10,964*</strong>
              </td>
            </tr>
            <tr>
              <td><strong>Nonresidents</strong></td>
              <td>
                <strong>$32,927*</strong>
              </td>
            </tr>
            <tr>
              <td><strong>Standard housing and meal plans</strong></td>
              <td>
                <strong>$12,616**</strong>
              </td>
            </tr>
            </tbody>
          </table>

          <p><br />
            <small>* Tuition and fees vary by academic program. Tuition and fees listed include a one-time University Records and Documents Fee of $225 for new students.<br/>** Based on a weighted room average and unlimited (Gold) meal plan</small>
          </p>

          <p>
            <a href="http://financialaid.uiowa.edu" class="bttn bttn--secondary bttn--caps">
              Financial Aid
              <i class="fas fa-arrow-right"></i>
            </a>
          </p>
          <p>
            Submit the <strong>Free Application for Federal Student Aid (FAFSA)</strong> early to maximize your available assistance.
          </p>
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
            <span class="headline__heading">Apply for housing and dining.</span>
          </h3>

          <p>Access the housing application through your admissions profile on
            <a data-cke-saved-href="https://myui.uiowa.edu" href="https://myui.uiowa.edu">MyUI</a>
            and pay the nonrefundable $75 housing application fee.
            <br>
          </p>
          <p>We have a number of housing options available to suit your ideal student experience. We strongly recommend applying for housing early. Apply by May 1, 2024 for the opportunity to request a roommate and select your room.</p>

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

  <div class="image-grid">
    <div class="image-grid__section">
    <img class="card__img" :src="'/images/viewbook/sections/0849.jpg'" alt="Alt Text" loading=lazy>
    </div>

    <div class="image-grid__section">
    <img class="card__img" :src="'/images/viewbook/sections/dormCropped.jpg'" alt="Alt Text" loading=lazy>
    </div>

    <div class="image-grid__section">
      <Modal>
        <template v-slot:modal-trigger>
        <img class="card__img" :src="'/images/viewbook/sections/Pano7.jpg'" alt="Alt Text" loading=lazy>
        </template>
        <template v-slot:modal-content>
        <img :src="'/images/viewbook/sections/2022_09_26-Pentacrest Drone Images at Sunrise-ksmurray-05.jpg'" alt="Alt Text" loading=lazy>
        </template>
      </Modal>
    </div>

    <div class="image-grid__section grid__content bg-pattern--brain-reversed">
      <headline
        headline_level="h2"
        headline_class="headline headline--uppercase"
        headline="It's <span>Great</span> to<br /> be a Hawkeye"
      />
    </div>

    <div class="image-grid__section">
    <img class="card__img" :src="'/images/viewbook/sections/2023_07_06-Summer Lifestyle, July 2023 jatorner -2424 Cropped.jpg'" alt="Alt Text" loading=lazy>>
    </div>

    <div class="image-grid__section">
    <img class="card__img" :src="'/images/viewbook/sections/2018_02_06-Snow Lifestyle Shoot-jatorner-0430 Cropped.jpg'" alt="Alt Text" loading=lazy>
    </div>
  </div>

  <footerSection
    :contact_info="contact_info"
    :social_media_links="social_media_links"
  />

</template>

<script>
import Banner from './components/Banner.vue';
import Stat from './components/Stat.vue';
import IowaBar from './components/IowaBar.vue';
import GridPanel from './components/GridPanel.vue';
import Headline from './components/Headline.vue';
import verticalDots from './components/verticalDots.vue';
import linkButton from './components/linkButton.vue';
import Aerial from './components/Aerial.vue';
import menuGroup from './components/menuGroup.vue';
import footerSection from './components/footerSection.vue';
import Modal from './components/Modal.vue';

export default {
  name: 'App',

  components: {
    Banner,
    Stat,
    IowaBar,
    Headline,
    verticalDots,
    GridPanel,
    linkButton,
    Aerial,
    menuGroup,
    Modal,
    footerSection
  },

  data() {
    return {
      areas_of_study: [
        {
          headline: 'Business, Economics, and Management',
          image: '/images/viewbook/areas/1.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/biz-econ-mgmt',
        },
        {
          headline: 'Education',
          image: '/images/viewbook/areas/2.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/edu',
        },
        {
          headline: 'Engineering and Computing',
          image: '/images/viewbook/areas/3.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/engr-comp',
        },
        {
          headline: 'Health Sciences',
          image: '/images/viewbook/areas/4.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/health-sci',
        },
        {
          headline: 'Languages, culture, and society',
          image: '/images/viewbook/areas/5.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/lang-cult-soc',
        },
        {
          headline: 'Life and natural sciences',
          image: '/images/viewbook/areas/6.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/life-nat-sci',
        },
        {
          headline: 'Math and quantitative sciences',
          image: '/images/viewbook/areas/7.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/math-quant-sci',
        },
        {
          headline: 'Preprofessional programs',
          image: '/images/viewbook/areas/8.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/preprofessional',
        },
        {
          headline: 'Social sciences and policy',
          image: '/images/viewbook/areas/9.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/soc-sci-pol',
        },
        {
          headline: 'Visual and performing arts',
          image: '/images/viewbook/areas/10.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/vis-perf-arts',
        },
        {
          headline: 'Writing, communications, literature, and media',
          image: '/images/viewbook/areas/11.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/write-comm-media',
        },
        {
          headline: '',
          button_text: 'Browse by Major',
          button_link: 'https://admissions.uiowa.edu/academics/undergraduate-areas-of-study',
        }
      ],
      stats_1: [
        {
          headline: '35',
          headline_prefix: '#',
          headline_suffix: '',
          stat_description: 'BEST PUBLIC UNIVERSITY BY U.S. NEWS & WORLD REPORT',
          stat_content: 'Among the top 2% of universities worldwide.',
        },
        {
          headline: '15:1',
          headline_prefix: '',
          headline_suffix: '',
          stat_description: 'STUDENT-TO-FACULTY RATIO',
          stat_content: 'Get to know your professors.',
        },
        {
          headline: '14',
          headline_prefix: '',
          headline_suffix: '',
          stat_description: 'INTERNATIONAL FULBRIGHT SCHOLARS IN 2023-24',
          stat_content: 'That’s the same as some Ivy League schools.',
        },
        {
          headline: '1 in 3',
          headline_prefix: '',
          headline_suffix: '',
          stat_description: 'UNDERGRADS PARTICIPATE IN RESEARCH',
          stat_content: 'Gain experience now.',
        }
      ],
      stats_2: [
        {
          headline: '600',
          headline_prefix: '',
          headline_suffix: '+',
          stat_description: 'STUDENT<br />  ORGANIZATIONS',
          stat_content: 'Or, start your own.',
        },
        {
          headline: '100',
          headline_prefix: '',
          headline_suffix: '+',
          stat_description: 'RESTAURANTS AND<br />  CAFÉS',
          stat_content: 'From vegan brunch to pie shakes.',
        },
        {
          headline: '400',
          headline_prefix: '',
          headline_suffix: '+',
          stat_description: 'ARTS PERFORMANCES Available EACH YEAR',
          stat_content: 'For $5 or less.',
        },
        {
          headline: '20',
          headline_prefix: '',
          headline_suffix: '',
          stat_description: 'NCAA DIVISION I<br />  TEAMS',
          stat_content: 'There’s nothing like a Hawkeye game.',
        }
      ],
      stats_3: [
        {
          headline: '97',
          headline_prefix: '',
          headline_suffix: '%',
          stat_description: 'OVERALL JOB/GRADUATE SCHOOL PLACEMENT RATE',
          stat_content: 'Business <strong>97%</strong><br />Education <strong>100%</strong><br />Engineering  <strong>97%</strong><br /> Liberal Arts and Sciences <strong>97%</strong><br /> Nursing <strong>99%</strong><br />Public Health <strong>100%</strong>',
        },
        {
          headline: '71,000',
          headline_prefix: '',
          headline_suffix: '+',
          stat_description: 'JOB, INTERNSHIP, AND VOLUNTEER OPPORTUNITIES AVAILABLE FOR STUDENTS EACH YEAR',
          stat_content: 'Everywhere from NASA to the Minnesota Vikings.',
        },
        {
          headline: '7,500',
          headline_prefix: '',
          headline_suffix: '+',
          stat_description: 'STUDENTS WORK ON CAMPUS ON AN ANNUAL BASIS',
          stat_content: 'Gain real-world skills that make résumés stand out.',
        },
        {
          headline: '70',
          headline_prefix: '',
          headline_suffix: '+',
          stat_description: 'COUNTRIES WHERE IOWA STUDENTS STUDIED ABROAD',
          stat_content: 'Students who study abroad are 26% more likely to graduate in 4 years.',
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
          section_title: 'Academic Opportunities',
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
    // Add the 'header-sticky' class so the iowa bar sticks to the top of the page.
    document.querySelector('body').classList.add('header-sticky');
  }
}
</script>

<style lang="scss">
$imgpath: '../node_modules/@uiowa/uids/src/assets/images';
@import '../node_modules/@uiowa/uids/src/assets/scss/reset.scss';
@import '../node_modules/@uiowa/uids/src/components/typography/lists/lists.scss';
@import '../node_modules/@uiowa/uids/src/components/tables/tables.scss';
@import '../node_modules/@uiowa/uids/src/components/typography/paragraph/paragraph.scss';
@import '../node_modules/@uiowa/uids/src/components/colors/colors.scss';
@import '../node_modules/@uiowa/uids/src/components/grid/grid.scss';
@import '../node_modules/@uiowa/uids/src/components/viewbook/grid-panel/grid-panel.scss';
@import '../node_modules/@uiowa/uids/src/components/card/card.scss';
@import '../node_modules/@uiowa/uids/src/components/layouts/viewbook/viewbook.scss';

.image-grid__section {
  line-height: 0;
}

.element--circle-list ul {
  margin-top: 1.05rem;
  margin-bottom: 1.05rem;
  margin-left: 1.875rem;
}

// Override and condense for smaller devices.
.cta-row__wrapper {
  transition: padding 0.5s ease;
  padding: 0.3rem 0;

  .cta-row__container .menu a {
    transition: margin 0.5s ease;
    margin: 0px .5rem;
    padding-bottom: 0.5rem;
  }

  .bttn--outline {
    border: none;
  }
}

@media (min-height: 1000px) {
  .cta-row__wrapper {
    padding: 1.875rem 0;
    .cta-row__container .menu a {
      margin: 0px 1.05rem;
    }

    .bttn--outline {
      border: 1px solid rgb(21, 21, 21);
    }
  }
}

// Stat fix to avoid inconsistent stacking below container breakpoint.
@media (max-width: 81.375em) and (min-width: 768px) {
  .stat--horizontal:not(.element--flex-center) .stat__description {
    flex-basis: 80%;
  }

  .stat--horizontal:not(.element--flex-center) .stat__content {
    flex-basis: 80%;
  }
}

</style>
