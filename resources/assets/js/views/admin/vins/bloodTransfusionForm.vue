<template>
<div class="container">
	<div class="page-header">
		<div class="row">
			<div class="col-md-6">
			<h1>Blood Transfusion Form</h1>
			</div>
			<div class="col-md-6">
				<div class="text-right">
					DOC NO. FMT/IPD/36 <br>
					REV. No. 0.1 <br>
					WEF 01-10-2014 <br>
					PAGE NO. 01 OF 02
				</div>
			</div>
		</div>
	</div>
	<form action="" method="post">

		<div class="form-group row">
				<div class="col">
					<label>Patient's Name:</label>
				</div>
				<div class="col">
					<input class="form-control" type="text"  name="patient_name" v-validate="'required'" v-model="bloodTransfusionDetails.patient_name" id="patient_name" value="" >
					<span class="help is-danger" v-show="errors.has('patient_name')">
						Field is required
					</span>
				</div>
				<div class="col">
					<label>IPD No.:</label>
				</div>
				<div class="col">
					<input type="text" class="form-control" name="ipd_no" v-validate="'required'" v-model="ipd_id" id="ipd_no" value="" >
					<span class="help is-danger" v-show="errors.has('ipd_no')">
						Field is required
					</span>
				</div>
		</div>

		<div class="form-group row">
			<div class="col">
				<label>Age:</label>
			</div>
			<div class="col">
				<input type="text" class="form-control" name="age" v-validate="'required'" v-model="bloodTransfusionDetails.age" id="age" value="" >
				<span class="help is-danger" v-show="errors.has('age')">
					Field is required
				</span>
			</div>
			<div class="col">
				<label>Sex:</label>
			</div>
			<div class="col">
				<select class="form-control" name="sex" v-validate="'required'" v-model="bloodTransfusionDetails.sex">
					<option value="NA">NA</option>
					<option value="male">Male</option>
					<option value="female">Female</option>
				</select>
				<span class="help is-danger" v-show="errors.has('sex')">
					Field is required
				</span>
			</div>
		</div>

		<div class="row form-group">
			<div class="col-md-6">
				<div class="col-md-6">
					<label>Date:</label>
				</div>
				<div class="col-md-6">
					<input type="date" class="form-control" name="date" v-validate="'required'" v-model="bloodTransfusionDetails.date" id="date" value="" >
					<span class="help is-danger" v-show="errors.has('date')">
						Field is required
					</span>
				</div>
			</div>
			<div class="col-md-6">
				<div class="col-md-6">
					<label>Time:</label>
				</div>
				<div class="col-md-6">
					<input type="time" class="form-control" name="time" v-validate="'required'" v-model="bloodTransfusionDetails.time" id="time" value="" >
					<span class="help is-danger" v-show="errors.has('time')">
						Field is required
					</span>
				</div>
			</div>
		</div>

		<div class="row form-group">
			<div class="col-md-6">
				<div class="col-md-6">
					<label>Patient's Blood Group:</label>
				</div>
				<div class="col-md-6">
					<select class="form-control" name="blood_group" v-validate="'required'" v-model="bloodTransfusionDetails.blood_group">
						<option value="A+">A+</option>
						<option value="A-">A-</option>
						<option value="AB+">AB+</option>
						<option value="AB-">AB-</option>
						<option value="B+">B+</option>
						<option value="B-">B-</option>
						<option value="O+">O+</option>
						<option value="O-">O-</option>
					</select>
					<span class="help is-danger" v-show="errors.has('blood_group')">
						Field is required
					</span>
				</div>
			</div>
			<div class="col-md-6">
				<div class="col-md-6">
					<label>History of previous BT :</label>
				</div>
				<div class="col-md-6">
					<select class="form-control" name="history_bt" v-validate="'required'" v-model="bloodTransfusionDetails.history_bt">
						<option value="NA">NA</option>
						<option value="Yes">Yes</option>
						<option value="No">No</option>
					</select>
					<span class="help is-danger" v-show="errors.has('history_bt')">
						Field is required
					</span>
				</div>
			</div>
		</div>


		<div class="row form-group">
			<div class="col-md-6">
				<label>If adverse reaction during previous transfusion and it's nature :</label>
			</div>
			<div class="col-md-6">
				<input type="text" class="form-control" name="adv" v-model="bloodTransfusionDetails.adv" id="adv" value="" >
			</div>
		</div>

		<hr>

		<div class="row form-group">
			<div class="col-md-6">
				<div class="col-md-6">
					<label>Blood Bag No.:</label>
				</div>
				<div class="col-md-6">
					<input type="text" class="form-control" name="blood_bag_no" v-validate="'required'" v-model="bloodTransfusionDetails.blood_bag_no" id="blood_bag_no" value="" >
					<span class="help is-danger" v-show="errors.has('blood_bag_no')">
						Field is required
					</span>
				</div>
			</div>
			<div class="col-md-6">
				<div class="col-md-6">
					<label>Blood Group:</label>
				</div>
				<div class="col-md-6">
					<select class="form-control" name="blood_bag_group" v-validate="'required'" v-model="bloodTransfusionDetails.blood_bag_group">
						<option value="A+">A+</option>
						<option value="A-">A-</option>
						<option value="AB+">AB+</option>
						<option value="AB-">AB-</option>
						<option value="B+">B+</option>
						<option value="B-">B-</option>
						<option value="O+">O+</option>
						<option value="O-">O-</option>
					</select>
					<span class="help is-danger" v-show="errors.has('blood_bag_group')">
						Field is required
					</span>
				</div>
			</div>
		</div>

		<div class="row form-group">
			<div class="col-md-6">
				<div class="col-md-6">
					<label>Product's Name:</label>
				</div>
				<div class="col-md-6">
					<select class="form-control" id="prod_name" name="prod_name" v-validate="'required'" v-model="bloodTransfusionDetails.prod_name">
							<option value="whole_blood"> Whole Blood </option>
							<option value="PCV"> PCV </option>
							<option value="PRC"> PRC </option>
							<option value="FFP"> FFP </option>
							<option value="SDP"> SDP </option>
							<option value="Cryoprecipitate"> Cryoprecipitate </option>
							<option value="OtherOther"> Other </option>
					</select>
					<span class="help is-danger" v-show="errors.has('prod_name')">
						Field is required
					</span>
				</div>
			</div>
			<div class="col-md-6">
				<div class="col-md-6">
					<label>Name of Blood Bank:</label>
				</div>
				<div class="col-md-6">
					<input type="text" class="form-control" name="name_blood_bank" v-validate="'required'" v-model="bloodTransfusionDetails.name_blood_bank" id="name_blood_bank1" value="" >
					<span class="help is-danger" v-show="errors.has('name_blood_bank')">
						Field is required
					</span>
				</div>
			</div>
		</div>

		<div class="row form-group">
			<div class="col-md-6">
				<div class="col-md-6">
					<label>Date of Expiry:</label>
				</div>
				<div class="col-md-6">
					<input type="date" class="form-control" name="expiry_date" v-validate="'required'" v-model="bloodTransfusionDetails.expiry_date" id="expiry_date" value="" >
					<span class="help is-danger" v-show="errors.has('expiry_date')">
						Field is required
					</span>
				</div>
			</div>
			<div class="col-md-6">
				<div class="col-md-6">
					<label>Checked by Dr.:</label>
				</div>
				<div class="col-md-6">
					<input type="text" class="form-control" name="checked_by" v-validate="'required'" v-model="bloodTransfusionDetails.checked_by" id="checked_by" value="" >
					<span class="help is-danger" v-show="errors.has('checked_by')">
						Field is required
					</span>
				</div>
			</div>
		</div>

		<div class="row form-group">
			<div class="col-md-6">
				<div class="col-md-6">
					<label>Unit Nurse:</label>
				</div>
				<div class="col-md-6">
					<input type="text" class="form-control" name="unit_nurse" v-validate="'required'" v-model="bloodTransfusionDetails.unit_nurse" id="unit_nurse" value="" >
					<span class="help is-danger" v-show="errors.has('unit_nurse')">
						Field is required
					</span>
				</div>
			</div>
		</div>

		<div class="row form-group">
			<div class="col-md-6">
				<div class="col-md-6">
					<label>BT Started at:</label>
				</div>
				<div class="col-md-6">
					<input type="time" class="form-control" name="start_time" v-validate="'required'" v-model="bloodTransfusionDetails.start_time" id="start_time" value="" >
					<span class="help is-danger" v-show="errors.has('start_time')">
						Field is required
					</span>
				</div>
			</div>
			<div class="col-md-6">
				<div class="col-md-6">
					<label>Stopped at:</label>
				</div>
				<div class="col-md-6">
					<input type="time" class="form-control" name="end_time" v-validate="'required'" v-model="bloodTransfusionDetails.end_time" id="end_time" value="" >
					<span class="help is-danger" v-show="errors.has('end_time')">
						Field is required
					</span>
				</div>
			</div>
		</div>

		<div class="row">
			<h3>Vital Chart:</h3>
		</div>
		<div class="row">
			<label>Vitals must be taken every 15 mins during transfusion and post transfusion upto 60 minutes.</label>
		</div>
		<div class="row">
			<table class="table table-bordered">
				<thead>
					<tr>
						<th></th>
						<th>Time</th>
						<th>Temp</th>
						<th>Resp</th>
						<th>BP</th>
					</tr>
				</thead>
				<tbody>
					<tr v-for="n in 15">

						<td v-if="n == 1" >Pre - Transfusion</td>
						<td v-else-if="n == 3">During Transfusion</td>
						<td v-else-if="n == 11">Post Transfusion</td>
						<td v-else></td>
						<td><input type="time" class="form-control" :name="'tftime'+n" v-model="bloodTransfusionDetails.transfusion[n].tftime" id="_01_01" /></td>
						<td><input type="text" class="form-control" :name="'temp'+n" v-model="bloodTransfusionDetails.transfusion[n].temp" id="_01_02" /></td>
						<td><input type="text" class="form-control" :name="'resp'+n" v-model="bloodTransfusionDetails.transfusion[n].resp" id="_01_03" /></td>
						<td><input type="text" class="form-control" :name="'bp'+n" v-model="bloodTransfusionDetails.transfusion[n].bp" id="_01_04" /></td>
					</tr>

				</tbody>
			</table>
		</div>

			<div class="row form-group">
				<div class="col-md-6">
					<div class="col-md-6">
						<label>Minor Reaction : </label>
					</div>
					<div class="col-md-6">
						<select class="form-group" name="minor_reaction" v-model="bloodTransfusionDetails.minor_reaction">
							<option value="skin_rash">Skin Rash</option>
							<option value="urticaria">Urticaria</option>
							<option value="body_ache">Body Ache</option>
							<option value="nausea">Nausea</option>
							<option value="abdominal_pain">Abdominal Pain</option>
						</select>
					</div>
				</div>
				<div class="col-md-6">
					<div class="col-md-6">
						<label>Moderate : </label>
					</div>
					<div class="col-md-6">
						<select class="form-group" name="moderate" v-model="bloodTransfusionDetails.moderate">
							<option value="fever">Fever</option>
							<option value="vomiting">Vomiting</option>
							<option value="shivering">Shivering</option>
							<option value="drowsieness">Drowsieness</option>
						</select>
					</div>
				</div>
			</div>

			<div class="row form-group">
				<div class="col-md-6">
					<div class="col-md-6">
						<label>Major Reaction : </label>
					</div>
					<div class="col-md-6">
						<select class="form-group" name="major_reactions" v-model="bloodTransfusionDetails.major_reactions">
							<option value="chest_pain">Chest Pain</option>
							<option value="breathlessness">Breathlessness</option>
							<option value="decreased_urine_output">Decreased Urine Output</option>
						</select>
					</div>
				</div>
				<div class="col-md-6">
					<div class="col-md-6">
						<label>Time of onset of Adverse Reactions : </label>
					</div>
					<div class="col-md-6">
						<input class="form-control" type="time" name="time_adverse" v-model="bloodTransfusionDetails.time_adverse" value=""/>
					</div>
				</div>
			</div>

		<div class="row form-group">
			<button class="btn btn-success" type="button" @click="saveBloodTransfusion()" >Submit</button>
		</div>
	</form>
</div>
</template>
<script >
	import User from '../../../api/users.js';
    export default {
        data() {
            return {
                'footer' : 'footer',
                'currentYear': new Date().getFullYear(),
								'type': 'bloodTransfusionForm',
                'patient_id': this.$store.state.Patient.patientId,
               	'ipd_id': this.$store.state.Patient.ipdId,
                'bloodTransfusionDetails' : {
									'patient_name': '',
									'ipd_no': '',
									'age': '',
									'sex': '',
									'date': '',
									'time': '',
									'blood_group': '',
									'history_bt': '',
									'adv': '',
									'blood_bag_no': '',
									'blood_bag_group': '',
									'prod_name': '',
									'name_blood_bank': '',
									'expiry_date': '',
									'checked_by': '',
									'unit_nurse': '',
									'start_time': '',
									'end_time': '',
									'minor_reaction': '',
									'moderate': '',
									'major_reactions': '',
									'time_adverse': '',
									'transfusion' : {
										'1':{
											'tftime' : '',
											'temp' : '',
											'resp' : '',
											'bp' : '',
										},
										'2':{
											'tftime' : '',
											'temp' : '',
											'resp' : '',
											'bp' : '',
										},
										'3':{
											'tftime' : '',
											'temp' : '',
											'resp' : '',
											'bp' : '',
										},
										'4':{
											'tftime' : '',
											'temp' : '',
											'resp' : '',
											'bp' : '',
										},
										'5':{
											'tftime' : '',
											'temp' : '',
											'resp' : '',
											'bp' : '',
										},
										'6':{
											'tftime' : '',
											'temp' : '',
											'resp' : '',
											'bp' : '',
										},
										'7':{
											'tftime' : '',
											'temp' : '',
											'resp' : '',
											'bp' : '',
										},
										'8':{
											'tftime' : '',
											'temp' : '',
											'resp' : '',
											'bp' : '',
										},
										'9':{
											'tftime' : '',
											'temp' : '',
											'resp' : '',
											'bp' : '',
										},
										'10':{
											'tftime' : '',
											'temp' : '',
											'resp' : '',
											'bp' : '',
										},
										'11':{
											'tftime' : '',
											'temp' : '',
											'resp' : '',
											'bp' : '',
										},
										'12':{
											'tftime' : '',
											'temp' : '',
											'resp' : '',
											'bp' : '',
										},
										'13':{
											'tftime' : '',
											'temp' : '',
											'resp' : '',
											'bp' : '',
										},
										'14':{
											'tftime' : '',
											'temp' : '',
											'resp' : '',
											'bp' : '',
										},
										'15':{
											'tftime' : '',
											'temp' : '',
											'resp' : '',
											'bp' : '',
										},

									}

                }
            }
        },
        methods: {
		    GetSelectComponent(componentName) {
		       this.$router.push({name: componentName})
		    },
		    saveBloodTransfusion() {
		    	this.$validator.validateAll().then(
	            (response) => {
	            	if (!this.errors.any()) {
	            		 $("body .js-loader").removeClass('d-none');
									 var bloodTransfusionDetails = {'type':this.type,'patient_id':this.patient_id,'ipd_id':this.ipd_id,'form_data':this.bloodTransfusionDetails};
				    	User.saveBloodTransfusion(bloodTransfusionDetails).then(
		                (response) => {
		                	if(response.data.status == 200) {
		                		toastr.success('Blood Transfusion details have been saved', 'Blood Transfusion Form', {timeOut: 5000});
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
