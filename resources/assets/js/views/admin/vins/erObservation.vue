<template>
<div class="container">
	<div class="page-header">
		<div class="row">
			<div class="col-md-6">
			<h1>ER Observation</h1>
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

	<hr>

	<form action="" method="post">

		<div class="row form-group">
			<div class="col-md-6">
				<div class="row">
					<div class="col-md-6">
						<label for="">IPD No.</label>
					</div>
					<div class="col-md-6">
						<input type="text" class="form-control" name="ipd_no" value="" v-model="ipd_id" v-validate="'required'">
						<span class="help is-danger" v-show="errors.has('ipd_no')">
							Field is required
						</span>
					</div>
				</div>
			</div>
		</div>
		<div class="row form-group">
			<div class="col-md-6">
				<div class="row">
					<div class="col-md-6">
						<label for="date">Date : </label>
					</div>
					<div class="col-md-6">
						<input class="form-control" type="date" name="date" value="" />
					</div>
				</div>
			</div>
			<div class="col-md-6">
				<div class="row">
					<div class="col-md-6">
						<label for="triage_category" class="control-label">Triage Category : </label>
					</div>
					<div class="col-md-6">
						<input class="form-control" type = "text" v-validate="'required'" id = "triage_category" name="triage_category" value=""  v-model="erObservationData.triage_category"/>
						<span class="help is-danger" v-show="errors.has('triage_category')">
							Field is required
						</span>
					</div>
				</div>
			</div>
		</div>

		<div class="row form-group">
			<div class="col-md-6">
				<div class="row">
					<div class="col-md-6">
						<label for="diagnosis" class="control-label">Diagnosis : </label>
					</div>
					<div class="col-md-6">
						<input class="form-control" type = "text" v-validate="'required'" id = "diagnosis" name="diagnosis" value=""  v-model="erObservationData.diagnosis"/>
						<span class="help is-danger" v-show="errors.has('diagnosis')">
							Field is required
						</span>
				</div>
				</div>
			</div>
			<div class="col-md-6">
				<div class="row">
					<div class="col-md-6">
						<label for="investigation" class="control-label">Investigations : </label>
					</div>
					<div class="col-md-6">
						<input class="form-control" type = "text" v-validate="'required'" id = "investigation" name="investigation" value=""  v-model="erObservationData.investigation"/>
						<span class="help is-danger" v-show="errors.has('investigation')">
							Field is required
						</span>
				</div>
				</div>
			</div>
		</div>

		<hr>

		<div class="row form-group">
			<table class="table table-bordered">
				<thead>
					<tr>
						<th>Time </th>
						<th v-for="ti in 3">
							<input class="form-control" type="time" :name="'time_'+ti" value=" " v-model="erObservationData.vitals.time[ti]" v-validate="'required'">
							<span class="help is-danger" v-show="errors.has('time_'+ti)">
								Field is required
							</span>
						</th>
					</tr>
				</thead>
				<tbody>
					<tr>
						<th>Pulse </th>
						<td v-for="pul in 3">
							<input class="form-control" type="text" :name="'pulse_'+pul" value=""  v-model="erObservationData.vitals.pulse[pul]" v-validate="'required'">
							<span class="help is-danger" v-show="errors.has('pulse_'+pul)">
								Field is required
							</span>
						</td>
					</tr>
					<tr>
						<th>BP </th>
						<td v-for="bpc in 3">
							<input class="form-control" type="text" :name="'bp_'+bpc" value=" " v-model="erObservationData.vitals.bp[bpc]" v-validate="'required'">
							<span class="help is-danger" v-show="errors.has('bp_'+bpc)">
								Field is required
							</span>
						</td>
					</tr>
					<tr>
						<th>SPO2 </th>
						<td v-for="spo2c in 3">
							<input class="form-control" type="text" :name="'spo2_'+spo2c" value=" " v-model="erObservationData.vitals.spo2[spo2c]" v-validate="'required'">
							<span class="help is-danger" v-show="errors.has('spo2_'+spo2c)">
								Field is required
							</span>
						</td>
					</tr>
					<tr>
						<th>RR </th>
						<td v-for="rrc in 3">
							<input class="form-control" type="text" :name="'rr_'+rrc" value=" "  v-model="erObservationData.vitals.rr[rrc]" v-validate="'required'">
							<span class="help is-danger" v-show="errors.has('rr_'+rrc)">
								Field is required
							</span>
						</td>
					</tr>
					<tr>
						<th>GCS </th>
						<td v-for="gcsc in 3">
							<input class="form-control" type="text" :name="'gcs_'+gcsc" value=" " v-model="erObservationData.vitals.gcs[gcsc]" v-validate="'required'">
							<span class="help is-danger" v-show="errors.has('gcs_'+gcsc)">
								Field is required
							</span>
						</td>
					</tr>
					<tr>
						<th>Temperature </th>
						<td v-for="tempc in 3">
							<input class="form-control" type="text" :name="'temp_'+tempc" value=" " v-model="erObservationData.vitals.temp[tempc]" v-validate="'required'">
							<span class="help is-danger" v-show="errors.has('temp_'+tempc)">
								Field is required
							</span>
						</td>
					</tr>
				</tbody>
			</table>
		</div>

		<hr />

		<div class="row form-group">
			<table class="table table-bordered">
				<thead>
					<tr>
						<th> IV Infusion</th>
						<th> QTY</TH>
						<th> Start Time</th>
						<th> End Time</th>
						<th> Remarks</th>
					</tr>
				</thead>
				<tbody>
					<tr v-for="m in 4">
						<td>
							<input type="text" :name="'iv_infusion_'+m" class="form-control" value=" " v-model="erObservationData.iv[m].iv_infusion">
					 </td>
						<td>
							<input type="text" :name="'quantity_'+m" class="form-control" value=" " v-model="erObservationData.iv[m].quantity">
					 </td>
						<td>
							<input type="time" :name="'start_time_'+m"  class="form-control" value=" " v-model="erObservationData.iv[m].start_time">
					</td>
						<td>
							<input type="time" :name="'end_time_'+m"  class="form-control" value=" " v-model="erObservationData.iv[m].end_time">
					</td>
						<td>
							<input type="text" :name="'remarks_'+m" class="form-control" value=" " v-model="erObservationData.iv[m].remarks">
					 </td>
					</tr>
				</tbody>
			</table>
		</div>

		<hr />
		<div class="row">
			<h3>Medication Administration</h3>
		</div>

		<div class="row form-group">
			<table class="table table-bordered">
				<thead>
					<tr>
						<th>Name of the Drug</th>
						<th>Dosage</TH>
						<th>Routine</th>
						<th>Administration By</th>
						<th>Time</th>
					</tr>
				</thead>
				<tbody>
					<tr v-for="n in 5">
						<td>
							<input type="text" :name="'name_drug_'+n" class="form-control" value=" " v-model="erObservationData.medication_administration[n].name_drug">
						</td>
						<td>
							<input type="text" :name="'dosage_'+n" class="form-control" value=" " v-model="erObservationData.medication_administration[n].dosage">
						</td>
						<td>
							<input type="text" :name="'routine_'+n" class="form-control" value=" " v-model="erObservationData.medication_administration[n].routine">
						</td>
						<td>
							<input type="text" :name="'administration_by_'+n"  class="form-control" value=" " v-model="erObservationData.medication_administration[n].administration_by">
						</td>
						<td>
							<input type="time" :name="'medication_time_'+n" class="form-control" value=" " v-model="erObservationData.medication_administration[n].medication_time">
						</td>
				  </tr>
				</tbody>
			</table>
		</div>

		<div class="row form-group">
			<div class="col-md-6">
				<div class="row">
					<div class="col-md-6">
						<label for="patient_shifted_to" class="control-label">Patient shifted to :</label>
					</div>
					<div class="col-md-6">
						<input class="form-control" type = "text" v-validate="'required'" id = "patient_shifted_to" name="patient_shifted_to" value=""  v-model="erObservationData.patient_shifted_to"/>
						<span class="help is-danger" v-show="errors.has('patient_shifted_to')">
							Field is required
						</span>
					</div>
				</div>
			</div>
			<div class="col-md-6">
				<div class="row">
					<div class="col-md-6">
						<label for="er_nurse" class="control-label">ER nurse :</label>
					</div>
					<div class="col-md-6">
						<input class="form-control" type = "text" v-validate="'required'" id = "er_nurse" name="er_nurse" value=""  v-model="erObservationData.er_nurse"/>
						<span class="help is-danger" v-show="errors.has('er_nurse')">
							Field is required
						</span>
					</div>
				</div>
			</div>
		</div>
		<div class="form-group text-center">
			<button class="btn btn-success" type="button" @click="saveerObservation()">Submit</button>
		</div>
	</form>
</div>
</body>
</template>

<script >
	import User from '../../../api/users.js';
    export default {
        data() {
            return {
                'footer' : 'footer',
                'currentYear': new Date().getFullYear(),
								'type': 'erObservation',
                'patient_id': this.$store.state.Patient.patientId,
               	'ipd_id': this.$store.state.Patient.ipdId,
                'erObservationData' : {
									'date':'',
									'triage_category':'',
									'diagnosis':'',
									'investigation':'',
									'vitals':{
										'time':{
											'1':'',
											'2':'',
											'3':'',
										},
										'pulse':{
											'1':'',
											'2':'',
											'3':'',
										},
										'bp':{
											'1':'',
											'2':'',
											'3':'',
										},
										'spo2':{
											'1':'',
											'2':'',
											'3':'',
										},
										'rr':{
											'1':'',
											'2':'',
											'3':'',
										},
										'gcs':{
											'1':'',
											'2':'',
											'3':'',
										},
										'temp':{
											'1':'',
											'2':'',
											'3':'',
										}
									},
									'iv':{
										'1':{
											'iv_infusion':'',
											'quantity':'',
											'start_time':'',
											'end_time':'',
											'remarks':'',
										},

										'2':{
											'iv_infusion':'',
											'quantity':'',
											'start_time':'',
											'end_time':'',
											'remarks':'',
										},

										'3':{
											'iv_infusion':'',
											'quantity':'',
											'start_time':'',
											'end_time':'',
											'remarks':'',
										},

										'4':{
											'iv_infusion':'',
											'quantity':'',
											'start_time':'',
											'end_time':'',
											'remarks':'',
										},

									},
									'medication_administration':{
										'1':{
											'name_drug':'',
											'dosage':'',
											'routine':'',
											'administration_by':'',
											'medication_time':'',
										},

										'2':{
											'name_drug':'',
											'dosage':'',
											'routine':'',
											'administration_by':'',
											'medication_time':'',
										},

										'3':{
											'name_drug':'',
											'dosage':'',
											'routine':'',
											'administration_by':'',
											'medication_time':'',
										},

										'4':{
											'name_drug':'',
											'dosage':'',
											'routine':'',
											'administration_by':'',
											'medication_time':'',
										},

										'5':{
											'name_drug':'',
											'dosage':'',
											'routine':'',
											'administration_by':'',
											'medication_time':'',
										},

									},
									'patient_shifted_to':'',
									'er_nurse':''
                }
            }
        },
        methods: {
		    GetSelectComponent(componentName) {
		       this.$router.push({name: componentName})
		    },
		    saveerObservation() {
		    	this.$validator.validateAll().then(
	            (response) => {
	            	if (!this.errors.any()) {
	            		 $("body .js-loader").removeClass('d-none');
									 var erObsData = {'type':this.type,'patient_id':this.patient_id,'ipd_id':this.ipd_id,'form_data':this.erObservationData};
									 User.saveerObservation(erObsData).then(
										(response) => {
											if(response.data.code == 200) {
												toastr.success('ERObservation has been saved', 'erObservation', {timeOut: 5000});
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
