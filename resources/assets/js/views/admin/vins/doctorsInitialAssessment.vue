<template>
	<div class="container">
		<div class="page-header">
			<div class="row">
				<div class="col-md-6">
				<h1>Doctor's Initial Assessment</h1>
				</div>
				<div class="col-md-6">
					<div class="text-right">
						DOC NO. FMT/HIC/09 <br>
						REV. No. 0.1 <br>
						WEF 10-10-2015
					</div>
				</div>
			</div>
		</div>

		<form action="" method="post">

			<div class="row form-group">
				<div class="col-md-6">
					<div class="col-md-6">
						<label>IPD No : </label>
					</div>
					<div class="col-md-6">
						<input class="form-control" type="text" name="ipd_no" v-model="ipd_id" value="" />
					</div>
				</div>
				<div class="col-md-6">
					<div class="col-md-6">
						<label>History : </label>
					</div>
					<div class="col-md-6">
						<input class="form-control" type="text" name="history" v-model="doctorsInitialAssessmentData.history" value="" />
					</div>
				</div>
			</div>

			<div class="row form-group">
					<div class="col-md-6">
						<div class="col-md-6">
							<label>Past History : </label>
						</div>
						<div class="col-md-6">
							<input class="form-control" type="text" name="past_history" v-model="doctorsInitialAssessmentData.past_history" value=""/>
						</div>
					</div>
					<div class="col-md-6">
						<div class="col-md-6">
							<label>Allergic History : </label>
						</div>
						<div class="col-md-6">
							<input class="form-control" type="text" name="allergic_history" v-model="doctorsInitialAssessmentData.allergic_history" value=""/>
						</div>
					</div>
			</div>

			<div class="row">
				<h3>In case of Road Accident : </h3>
			</div>

			<div class="row form-group">
				<div class="col-md-6">
					<div class="col-md-6">
			      <label>Name of Informant : </label>
					</div>
					<div class="col-md-6">
			      <input class="form-control" type="text" name="name_informant" v-model="doctorsInitialAssessmentData.name_informant" value=""/>

					</div>
				</div>
				<div class="col-md-6">
					<div class="col-md-6">
			      <label>Brought By : </label>
					</div>
					<div class="col-md-6">
			      <input class="form-control" type="text" name="brought_by" v-model="doctorsInitialAssessmentData.brought_by" value=""/>

					</div>
				</div>
			</div>

			<div class="row form-group">
				<div class="col-md-6">
					<div class="col-md-6">
			      <label>Place of Accident : </label>
					</div>
					<div class="col-md-6">
			      <input class="form-control" type="text" name="place_of_accident" v-model="doctorsInitialAssessmentData.place_of_accident" value="" />
					</div>
				</div>
				<div class="col-md-6">
					<div class="col-md-6">
			      <label>Time : </label>
					</div>
					<div class="col-md-6">
			      <input class="form-control" type="time" name="current_time" v-model="doctorsInitialAssessmentData.current_time" value=""/>

					</div>
				</div>
			</div>

			<div class="row form-group">
				<div class="col-md-6">
					<div class="col-md-6">
			      <label>Date : </label>
					</div>
					<div class="col-md-6">
			      <input class="form-control" type="date" name="current_date" v-model="doctorsInitialAssessmentData.current_date" value=""/>

					</div>
				</div>
				<div class="col-md-6">
					<div class="col-md-6">
			      <label>MLC Done outside or not : </label>
					</div>
					<div class="col-md-6">
			      <select class="form-control" name="mlc" v-model="doctorsInitialAssessmentData.mlc" value="">
							<option value="no" >No</option>
							<option value="yes" >Yes</option>
						</select>

					</div>
				</div>
			</div>

			<hr>
			<div class="row">
				<h3>History Of : </h3>
			</div>

			<div class="row form-group">
				<div class="col-md-6">
					<div class="col-md-6">
			      <label>LOC : </label>
					</div>
					<div class="col-md-6">
						<select class="form-control" name="loc" v-model="doctorsInitialAssessmentData.loc" value="">
							<option value="no">No</option>
							<option value="yes">Yes</option>
						</select>

					</div>
				</div>
				<div class="col-md-6">
					<div class="col-md-6">
			      <label>ENT Bleeding : </label>
					</div>
					<div class="col-md-6">
						<select class="form-control" name="ent_bleeding" v-model="doctorsInitialAssessmentData.ent_bleeding" value="">
							<option value="no" >No</option>
							<option value="yes">Yes</option>
						</select>

					</div>
				</div>
			</div>

			<div class="row form-group">
				<div class="col-md-6">
					<div class="col-md-6">
			      <label>Seizures : </label>
					</div>
					<div class="col-md-6">
						<select class="form-control" name="seizures" v-model="doctorsInitialAssessmentData.seizures" value="">
							<option value="no" >No</option>
							<option value="yes" >Yes</option>
						</select>
					</div>
				</div>
				<div class="col-md-6">
					<div class="col-md-6">
			      <label>Vomiting : </label>
					</div>
					<div class="col-md-6">
						<select class="form-control" name="vomiting" v-model="doctorsInitialAssessmentData.vomiting" value="">
							<option value="no">No</option>
							<option value="yes">Yes</option>
						</select>
					</div>
				</div>
			</div>
			<hr>

			<div class="row">
				<h3>Vitals : </h3>
			</div>

			<div class="row form-group">
				<div class="col-md-6">
					<div class="col-md-6">
			      <label>Pulse : </label>
					</div>
					<div class="col-md-6">
			      <input class="form-control" type="text" name="pulse" v-model="doctorsInitialAssessmentData.pulse" value=""/>
					</div>
				</div>
				<div class="col-md-6">
					<div class="col-md-6">
			      <label>Temprature : </label>
					</div>
					<div class="col-md-6">
			      <input class="form-control" type="text" name="temp" v-model="doctorsInitialAssessmentData.temp" value="" />
					</div>
				</div>
			</div>

			<div class="row form-group">
				<div class="col-md-6">
					<div class="col-md-6">
			      <label>BP : </label>
					</div>
					<div class="col-md-6">
			      <input class="form-control" type="text" name="bp" v-model="doctorsInitialAssessmentData.bp" value=""/>
					</div>
				</div>
				<div class="col-md-6">
					<div class="col-md-6">
			      <label>SPO2 : </label>
					</div>
					<div class="col-md-6">
			      <input class="form-control" type="text" name="spo2" v-model="doctorsInitialAssessmentData.spo2" value=""/>
					</div>
				</div>
			</div>

			<div class="row form-group">
				<div class="col-md-6">
					<div class="col-md-6">
			      <label>RBS : </label>
					</div>
					<div class="col-md-6">
						<input class="form-control" type="text" name="rbs" v-model="doctorsInitialAssessmentData.rbs" value=""/>
					</div>
				</div>
				<div class="col-md-6">
					<div class="col-md-6">
			      <label>Pain : </label>
					</div>
					<div class="col-md-6">
						<select class="form-control" name="pain" v-model="doctorsInitialAssessmentData.pain" value="">
							<option value="no" >No</option>
							<option value="yes" >Yes</option>
						</select>
					</div>
				</div>
			</div>

			<div class="row form-group">
				<div class="col-md-6">
					<div class="col-md-6">
			      <label>GCS : </label>
					</div>
					<div class="col-md-6">
			      <input class="form-control" type="text" name="gcs_e" v-model="doctorsInitialAssessmentData.gcs_e" value=""/>
					</div>
				</div>
				<div class="col-md-6">
					<div class="col-md-6">
			      <input class="form-control" type="text" name="gcs_m" v-model="doctorsInitialAssessmentData.gcs_m" value=""/>
					</div>
					<div class="col-md-6">
			      <input class="form-control" type="text" name="gcs_v" v-model="doctorsInitialAssessmentData.gcs_v" value=""/>
					</div>
				</div>
			</div>

			<div class="row form-group">
				<div class="col-md-6">
					<div class="col-md-6">
						<label>Systematic Examination : </label>
					</div>
					<div class="col-md-6">
						<input class="form-control" type="text" name="systematic_examination" v-model="doctorsInitialAssessmentData.systematic_examination" value=""/>
					</div>
				</div>
				<div class="col-md-6">
					<div class="col-md-6">
						<label>Any other Findings or Injuries : </label>
					</div>
					<div class="col-md-6">
						<input class="form-control" type="text" name="any_other" v-model="doctorsInitialAssessmentData.any_other" value=""/>
					</div>
				</div>
			</div>

			<div class="row form-group">
				<div class="col-md-6">
					<div class="col-md-6">
						<label>Treated on Admission : </label>
					</div>
					<div class="col-md-6">
						<input class="form-control" type="text" name="treated_on_admission" v-model="doctorsInitialAssessmentData.treated_on_admission" value=""/>
					</div>
				</div>
				<div class="col-md-6">
					<div class="col-md-6">
						<label>Shifted To : </label>
					</div>
					<div class="col-md-6">
						<input class="form-control" type="text" name="shifted_to" v-model="doctorsInitialAssessmentData.shifted_to" value=""/>
					</div>
				</div>
			</div>
			<div class="text-center form-group">
				<button class="btn btn-success" type="button" @click="saveDoctorsInitialAssessment()">Submit</button>
			</div>

		</form>
	</div>
</template>
<script >
	import User from '../../../api/users.js'
    export default {
        data() {
            return {
                'footer' : 'footer',
                'currentYear': new Date().getFullYear(),
								'type': 'doctorsInitialAssessment',
                'patient_id': this.$store.state.Patient.patientId,
               	'ipd_id': this.$store.state.Patient.ipdId,
								'doctorsInitialAssessmentData': {
									'history' : '',
									'past_history' : '',
									'allergic_history' : '',
									'name_informant' : '',
									'brought_by' : '',
									'place_of_accident' : '',
									'current_time' : '',
									'current_date' : '',
									'mlc' : '',
									'loc' : '',
									'ent_bleeding' : '',
									'seizures' : '',
									'vomiting' : '',
									'pulse' : '',
									'temp' : '',
									'bp' : '',
									'spo2' : '',
									'rbs' : '',
									'pain' : '',
									'gcs_e' : '',
									'gcs_m' : '',
									'gcs_v' : '',
									'systematic_examination' : '',
									'any_other' : '',
									'treated_on_admission' : '',
									'shifted_to' : '',
								}
            }
        },
				methods: {
		    GetSelectComponent(componentName) {
		       this.$router.push({name: componentName})
		    },
		    saveDoctorsInitialAssessment() {
		    	this.$validator.validateAll().then(
	            (response) => {
	            	if (!this.errors.any()) {
	            		 $("body .js-loader").removeClass('d-none');
                   var doctorsInitialAssessmentData = {'type':this.type,'patient_id':this.patient_id,'ipd_id':this.ipd_id,'form_data':this.doctorsInitialAssessmentData};
				    	User.saveDoctorsInitialAssessment(doctorsInitialAssessmentData).then(
		                (response) => {
		                	if(response.data.status == 200) {
		                		toastr.success('Doctors Initial Assessment has been saved', 'Doctors Initial Assessment', {timeOut: 5000});
		                	}
		                	 $("body .js-loader").addClass('d-none');

		                },
		                (error) => {
		                	 $("body .js-loader").addClass('d-none');

		                }
		                )
			    	}
			    },
                (error) => {
                }
                )

			}
		  },

    }
</script>
