<template>
	<div class="container" style="width: 100%">
		<!-- COVER IMAGE AND FLOATING BUTTON -->
		<div class="cover-image"></div>	
		<div class="desktop-fab-container ">
			<!-- REPLACE WITH YOUR APP URL -->
 			<a href="YOUR_APP_URL_HERE">
 				<paper-fab class="wow fadeInUp desktop-fab" icon="shop"></paper-fab>
 			</a>
		</div>
		
		<!-- ICON, NAME AND DESCRIPTION -->
		<div class="wow fadeInUp content-card">
			<!-- REPLACE WITH YOUR APP URL -->
			<a href="YOUR_APP_URL_HERE">
				<paper-fab class="mobile-fab" icon="shop"></paper-fab>
			</a>
			
			<div class="icon-and-title-flex">
				<img src="https://github.com/FaizMalkani/appsite/blob/master/img/otherapps/placeholder_four.png?raw=true" class="appicon"></img>
				<div class="title-container">
					<span class="text-title">Robo Advisors Comparison</span>
					<br><div class="intertext-padding"></div>
					<span class="text-subtitle">A Detailed Breakdown</span>
				</div>	
			</div><br><br>
			<span class="text-description" style="font-size: 1.1em">
				We’ve done a number of reviews of the different types of robo-advisors that are up-and-coming in the tech space. Now that we’ve done the research we’ve have gathered the data of robo advisors all in one place.
			</span>
		</div>

		<!-- OTHER APPS BY YOU -->
		<div class="wow fadeInUp content-works"> 
		    <div class="screenshot-item" @click="selected = 'betterment'">
                <img src="https://media.glassdoor.com/sqll/817462/betterment-squarelogo-1442314874156.png">
                <span class="tile-title">Betterment</span>
            </div>
            <div class="screenshot-item" @click="selected = 'turbo'">
                <img src="https://i.vimeocdn.com/portrait/8470889_300x300.jpg">
                <span class="tile-title">Turbo Advisor</span>
            </div>
            <div class="screenshot-item" @click="selected = 'wealthfront'">
                <img src="http://www.financemagnates.com/wp-content/uploads/2015/07/wealthfront-logo-400x400.png">
                <span class="tile-title">Wealth Front</span>
            </div>
            <div class="screenshot-item" @click="selected = 'personalcapital'">
                <img src="https://media.glassdoor.com/sqll/695964/personal-capital-squarelogo-1472078618877.png">
                <span class="tile-title">Personal Capital</span>
            </div>
            <div class="screenshot-item" @click="selected = 'acorns'">
                <img src="http://photos.prnewswire.com/prnfull/20141007/150849">
                <span class="tile-title">Acorns</span>
            </div>
 	    </div>

 	    <div class="wow fadeInUp content-works"> 
		    <div class="screenshot-item" @click="selected = 'charles'">
                <img src="https://upload.wikimedia.org/wikipedia/commons/a/a4/Charles_Schwab_Corporation_logo.png">
                <span class="tile-title">Charles Schwab</span>
            </div>
            <div class="screenshot-item" @click="selected = 'vanguard'">
                <img src="http://millennialmoney.com/wp-content/uploads/2015/09/vanguard.logo_.png">
                <span class="tile-title">Vanguard</span>
            </div>
            <div class="screenshot-item" @click="selected = 'fidelity'">
                <img src="https://media.licdn.com/mpr/mpr/shrink_200_200/AAEAAQAAAAAAAAQsAAAAJGQ4YzNhNWYxLTY3MjAtNDZjZS04MTA5LTJmZmNkZTlhYTM4ZQ.png">
                <span class="tile-title">Fidelity Go</span>
            </div>
            <div class="screenshot-item" @click="selected = 'sigfig'">
                <img src="https://www.sigfig.com/site/images/ngts-ui-web/common/logo-light.unrevved.png">
                <span class="tile-title">SigFig</span>
            </div>
            <div class="screenshot-item" @click="selected = 'tradeking'">
                <img src="https://yt3.ggpht.com/-IaPRb2qHOOQ/AAAAAAAAAAI/AAAAAAAAAAA/y9AbY6cuwSM/s900-c-k-no-mo-rj-c0xffffff/photo.jpg">
                <span class="tile-title">TradeKing</span>
            </div>
 	    </div>
	
	
	<!-- APP DETAILS -->
	<div class="wow fadeInUp content-card" style="margin-top: 0;">
 		<span class="text-subtitle" style="font-size: 2em; font-weight: 300; color: #333">{{ robo.name }}</span>
		<br><br>
		<div>
			<!-- REPLACE WITH YOUR APP DETAILS ACCORDINGLY -->
			<div class="detail-item">
				<i class="details-icon mdi mdi-logout-variant mdi-24px"></i>
				<span class="text-description"><a v-bind:href="robo.url">{{ robo.url }}</a></span>
			</div>
			<div class="detail-item">
				<i class="details-icon mdi mdi-history mdi-24px"></i>
				<span class="text-description">Founded in {{ robo.year }}<span>
			</div>
			<div class="detail-item">
				<i class="details-icon mdi mdi-currency-usd mdi-24px"></i>
				<span class="text-description">{{ robo.deposit | currency }} minimum deposit</span>
			</div>
			<div class="detail-item">
				<i class="details-icon mdi mdi-cash-multiple mdi-24px"></i>
				<span class="text-description">Assets: {{ robo.assets }}</span>
			</div>
			<div class="detail-item">
				<i class="details-icon mdi mdi-cash-usd mdi-24px"></i>
				<span class="text-description">Fees: {{ robo.fees }}</span>
			</div>
			<div class="detail-item">
				<i v-if="robo.tax" class="details-icon mdi mdi-checkbox-marked-circle-outline mdi-24px green"></i>
				<i v-if="!robo.tax" class="details-icon mdi mdi-close-circle-outline mdi-24px red"></i>
				<span class="text-description">Tax Loss Harvesting</span>
			</div>
			<div class="detail-item">
				<i v-if="robo.ira" class="details-icon mdi mdi-checkbox-marked-circle-outline mdi-24px green"></i>
				<i v-if="!robo.ira" class="details-icon mdi mdi-close-circle-outline mdi-24px red"></i>
				<span class="text-description">IRA / Roth IRA</span>
			</div>
		</div>	
 	</div>

 	<!-- SPACE BELOW DETAILS -->	
	<div class="empty-space">
		<div class="meta-container wow fadeInUp">
			<div class="wow fadeInUp detail-item watermark credits">
			</div>
		</div>	
	</div>
</template>

<script>

export default {
 	data() {
		return {
			advisors: {
				betterment: {
					name: 'Betterment',
					url: 'https://www.betterment.com',
					logo: '',
					year: 2007,
					assets: '$5.8 Billion',
					deposit: '$0',
					fees: '0.15% - 0.35% / yr',
					ira: true,
					tax: true
				},
				turbo: {
					name: 'Turbo Advisor',
					url: 'https://www.turboadvisor.com',
					logo: '',
					year: '2016',
					assets: '',
					deposit: '$0',
					fees: '0.25% annually',
					ira: true,
					tax: false
				},
				personalcapital: {
					name: 'Personal Capital',
					url: 'https://www.personalcapital.com',
					logo: '',
					year: '2011',
					assets: '$1.52 Billion',
					deposit: '$25,000',
					fees: '0.49% - 0.89% / yr',
					ira: true,
					tax: true
				},
				wealthfront: {
					name: 'Wealth Front',
					url: 'https://www.wealthfront.com',
					logo: '',
					year: '2008',
					assets: '$2.61 Billion',
					deposit: '$500',
					fees: 'None first $10k, 0.25% / yr for more',
					ira: true,
					tax: true
				},
				charles: {
					name: 'Charles Schwab',
					url: 'https://intelligent.schwab.com',
					logo: '',
					year: '2015',
					assets: '',
					deposit: '$5,000',
					fees: 'None',
					ira: true,
					tax: true
				}
				,
				vanguard: {
					name: 'Vanguard',
					url: 'https://investor.vanguard.com',
					logo: '',
					year: '2013',
					assets: '$101 Million',
					deposit: '$50,000',
					fees: 'None',
					ira: true,
					tax: false
				}
				,
				fidelity: {
					name: 'Fidelity Go',
					url: 'https://www.fidelity.com/go',
					logo: '',
					year: '',
					assets: '',
					deposit: '$5,000',
					fees: '0.35% - 0.40% / yr',
					ira: true,
					tax: false
				},
				sigfig: {
					name: 'SigFig',
					url: 'https://www.sigfig.com',
					logo: '',
					year: '2011',
					assets: '$70 Million',
					deposit: '$2,000',
					fees: 'None first $10k, 0.25% / yr for more',
					ira: true,
					tax: true
				},
				tradeking: {
					name: 'TradeKing Advisors',
					url: 'https://www.tradekingadvisors.com',
					logo: '',
					year: '2014',
					assets: '$8.3 Million',
					deposit: '$500',
					fees: '0.25% / yr',
					ira: true,
					tax: false
				}
			},
			selected: 'turbo'
		}
	},
	computed: {
		robo() {
			return this.advisors[this.selected];
		}
	}
}
</script>
