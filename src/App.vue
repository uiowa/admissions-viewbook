<template>
  <iowa-bar></iowa-bar>
  
  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="hero-banner"></div>
  </div>
  <div class="card__wrapper">
    <template v-for="(area, index) in areas_of_study">
      <hero :headline="area.headline"
            :image="area.image"
            :url="area.link_url"
            :class="getHeroClasses(index)"
      >
      </hero>
    </template>
  </div>

  <div data-uids-cta="data-uids-cta" role="region" class="cta-row__wrapper">
    <div class="cta-row__container">
      {% include "@menu" with {
        items : link_bttn.items | slice(0, 4)
      } %}
    </div>
  </div>

  {% include "@vertical-dots" with vertical_dots %}

  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="areas-of-study"></div>
  </div>
  <div class="asymmetrical-grid">
  <div class="asymmetrical-grid__content-left grid__content">
      <headline 
        heading_level= "h2"
        heading_class= "bold-headline--caps bold-headline"
        heading= "200+ Areas<br /> of Study"
      />
      <p>Iowa offers over 200 majors, minors and certificates. Students are encouraged to work across disciplines to find their passion</p>
  <a href="https://admissions.uiowa.edu/academics/undergraduate-areas-of-study" class="bttn bttn--secondary bttn--caps">
        View Areas of Study
        <i class="fas fa-arrow-right"></i>
      </a>
    </div>
  <div class="asymmetrical-grid__image-right">

      <div class="card__wrapper">
  {% for item in hero_row.items | slice(0, 12) %}
    {% include '@hero' with {
        'hero_title_classes': hero_title_classes,
        'hero_vertical_alignment': hero_vertical_alignment,
        'hero_horizontal_alignment': hero_horizontal_alignment,
        'hero_title': item.hero_title,
        'hero_text': item.hero_text,
        'hero_image': item.hero_image,
        'hero_type': hero_type,
        'hero_size': hero_size,
        'hero_overlay': hero_overlay,
        'hero_classes': item.hero_classes,
        'hero_link_url': item.hero_link_url,
        'hero_link_title': item.hero_link_title,
        'hero_link_classes': item.hero_link_classes,
      } %}
  {% endfor %}

      </div>
    </div>
  </div>



  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="academic-opportunities"></div>
  </div>

  <div class="asymmetrical-grid">
    <div class="asymmetrical-grid__image-left">
      <img class="card__img" src="src/assets/images/viewbook/sections/0315.jpg" alt="Alt Text">
    </div>
    <div class="asymmetrical-grid__content-right grid__content">
      <headline 
          heading_level= "h2"
          heading_class= "bold-headline--caps bold-headline"
          heading= "We Work <span>Together</span>"
      />
      <p>The University of Iowa blends big-school opportunities with close, personal support to help you excel. We remove the barriers between arts and science, between students and faculty—but most of all, between you and anything you’d like to explore.</p>
      <p>How many universities have both a state-of-the-art children’s hospital and
      a 3,883-pipe Klais organ? Or helped build the Voyager I satellite and the very first creative writing degree program? Just one: Iowa.</p>

      <a href="https://admissions.uiowa.edu/academics/academics" class="bttn bttn--secondary bttn--caps">
        View Academic Opportunities
        <i class="fas fa-arrow-right"></i>
      </a>
    </div>
  </div>


  <div class="stat__wrapper bg--black">

      {% for item in stat_row_1.items | slice(0, 4) %}
        {% include "@stat" with {
          "stat_classes" : item.stat_classes,
          "stat_image" : item.stat_image,
          "stat_image_position" : item.stat_image_position,
          "stat_pattern" : item.stat_pattern,
          "stat_title" : item.stat_title,
          "stat_prefix" : item.stat_prefix,
          "stat_suffix" : item.stat_suffix,
          "stat_summary" : item.stat_summary,
          "stat_content" : item.stat_content
        } %}
      {% endfor %}

  </div>

  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="iowa-city-life"></div>
  </div>
  {% render '@aerial' %}

  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="student-life"></div>
  </div>
  <div class="asymmetrical-grid">

  <div class="asymmetrical-grid__content-left grid__content">
    <headline 
      heading_level= "h2"
      heading_class= "bold-headline--caps bold-headline"
      heading= "MAKE <span>30,000</span> NEW FRIENDS"
    />
  <p>Big Ten athletics, theaters, music venues, 500+ student groups, community organizations, student philanthropy, hiking trails, bike paths, workout facilities, hundreds of restaurants and coffee shops and food carts and—you get the idea. There’s a lot to do in Iowa City. Every club, event, and activity is an opportunity to make new connections and find your own close-knit community on campus.</p>
  <a href="https://admissions.uiowa.edu/student-life/student-life" class="bttn bttn--secondary bttn--caps">

      View Student Life

      <i class="fas fa-arrow-right"></i>
    </a>

  </div>

  <div class="asymmetrical-grid__image-right">
    <img class="card__img" src="src/assets/images/viewbook/sections/1304.jpg" alt="Alt Text">
  </div>
  </div>


  <div class="stat__wrapper  bg--black">

      {% for item in stat_row_2.items | slice(0, 4) %}
        {% include "@stat" with {
          "stat_classes" : item.stat_classes,
          "stat_image" : item.stat_image,
          "stat_image_position" : item.stat_image_position,
          "stat_pattern" : item.stat_pattern,
          "stat_title" : item.stat_title,
          "stat_prefix" : item.stat_prefix,
          "stat_suffix" : item.stat_suffix,
          "stat_summary" : item.stat_summary,
          "stat_content" : item.stat_content
        } %}
      {% endfor %}
  </div>



  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="student-outcomes"></div>
  </div>
  <div class="asymmetrical-grid">

  <div class="asymmetrical-grid__image-left">

    <img class="card__img" src="src/assets/images/viewbook/sections/1961.jpg" alt="Alt Text">
  </div>

  <div class="asymmetrical-grid__content-right grid__content">
    <headline 
      heading_level= "h2"
      heading_class= "bold-headline--caps bold-headline"
      heading= "Make an <span>Impact</span>"
    />
  <p>Having big ideas isn’t enough—to excel in any career, you need to know how to share them and make them real. Iowa’s leadership in the study and craft of writing helps every Hawkeye learn communication skills that give them an edge. Dedicated career advising, thousands of on-campus job interviews, and countless opportunities for hands-on learning make Iowa grads stand out.</p>

  <a href="https://stories.uiowa.edu/student-outcomes" class="bttn bttn--secondary bttn--caps">
    View Student Outcomes
    <i class="fas fa-arrow-right"></i>
  </a>
  </div>
  </div>



  <div class="stat__wrapper  bg--black">

    {% for item in stat_row_3.items | slice(0, 4) %}
      {% include "@stat" with {
          "stat_classes" : item.stat_classes,
          "stat_image" : item.stat_image,
          "stat_image_position" : item.stat_image_position,
          "stat_pattern" : item.stat_pattern,
          "stat_title" : item.stat_title,
          "stat_prefix" : item.stat_prefix,
          "stat_suffix" : item.stat_suffix,
          "stat_summary" : item.stat_summary,
          "stat_content" : item.stat_content
        } %}
    {% endfor %}
  </div>

  <div class="v-dots-scroll-spacer">
    <div class="v-dots-scroll-target" id="five-step"></div>
  </div>
  <div class="split-grid">
  <div class="split-grid__column grid__content">
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

  <p><strong>RAI FORMULA:</strong></p>
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
    <strong>ACT and SAT Test Scores:</strong></p>
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

  <div class="split-grid__column grid__content">


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






  {% embed '@footer' %}


  {% endembed %}






</template>

<script>
import Hero from './components/Hero.vue';
import IowaBar from './components/IowaBar.vue';
import headline from './components/headline.vue';

export default {
  name: 'App',
  components: {
    Hero,
    IowaBar,
    headline
  },
  data() {
    return {
      areas_of_study: [
        {
          headline: 'Business, Economics, and Management',
          image: 'https://uids.brand.uiowa.edu/branches/feature_admissions_viewbook/assets/images/viewbook/areas/1.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/biz-econ-mgmt',
        },
        {
          headline: 'Education',
          image: 'https://uids.brand.uiowa.edu/branches/feature_admissions_viewbook/assets/images/viewbook/areas/2.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/edu',
        },
        {
          headline: 'Engineering and Computing',
          image: 'https://uids.brand.uiowa.edu/branches/feature_admissions_viewbook/assets/images/viewbook/areas/3.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/engr-comp',
        },
        {
          headline: 'Health Sciences',
          image: 'https://uids.brand.uiowa.edu/branches/feature_admissions_viewbook/assets/images/viewbook/areas/4.jpg',
          link_url: 'https://admissions.uiowa.edu/academics/health-sci',
        },
        {
          headline: '',
          image: '',
          link_url: 'https://admissions.uiowa.edu/academics/undergraduate-areas-of-study',
        }
      ],
    }
  },
  methods: {
    getHeroClasses(index) {
      console.log('index', index);
      console.log('count', this.areas_of_study.length);
      let classes = 'hero--solid-opacity hero--large hero--row hero--vertical-bottom hero--horizontal-left';
      if (index+1 >= this.areas_of_study.length) {
        classes += ' bg-pattern--brain-black';
      }
      return classes;
    }
  }
}
</script>

<style lang="scss" scoped>
  $imgpath: '../node_modules/@uiowa/uids/src/assets/images';
  @import '../node_modules/@uiowa/uids/src/components/colors/colors.scss';
  @import '../node_modules/@uiowa/uids/src/components/layouts/viewbook/viewbook';
</style>