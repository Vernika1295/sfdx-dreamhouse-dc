#!groovy
import groovy.json.JsonSlurperClassic
//#!/usr/bin/env groovy 
import java.net.URL

// Declarative // 
pipeline {   
  agent any
    stages {   
	    
  stage('Build') {         
  steps {  
	  
  echo 'Building..'      
  }       
  }    
  stage('Test') {   
  steps {     
  echo 'Testing..'   
  }         }     
  stage('Deploy') { 
              steps { 
                  echo 'Deploying....'      
  }         }     } } // Script // node {  
  stage('Build') {         echo 'Building....'     }     stage('Test') {     
    echo 'Building....'   
	}     stage('Deploy')
	{         echo 'Deploying....'   
	} }
	// Script // node 
	{  
	checkout scm 
	    /* .. snip .. */ } 
	// Declarative not yet implemented //
// Declarative // pipeline {     agent any
    stages {         stage('Build') {             steps { 
                sh 'make'          
    archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true        
	}         }     } } // Script // node {     stage('Build') {       
	sh 'make'         archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true    
	} }
// Declarative // pipeline {     agent any
    stages {         stage('Test') {             steps {    
             /* `make check` returns non-zero on test failures,            
			 * using `true` to allow the Pipeline to continue nonetheless */  
	    
			 sh 'make check || true'                  junit '**/target/*.xml'          
			 }    
				   }     } }
// Script // 
			 node
			 {     /* .. snip .. */   
			 stage('Test') {   
			 /* `make check` returns non-zero on test failures,  
			 * using `true` to allow the Pipeline to continue nonetheless 
			          */         sh 'make check || true'        junit '**/target/*.xml' 
			 }     /* .. snip .. */ }
