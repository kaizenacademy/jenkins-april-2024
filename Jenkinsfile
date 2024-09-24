template = '''
apiVersion: v1
kind: Pod
metadata:
  name: kubernetes
  labels:
    run: kubernetes
spec:
  serviceAccount: kubernetes
  containers:
  - name: kubernetes
    image: kaizenacademy/bin:1.0.0
    '''

podTemplate(cloud: 'kubernetes', label: 'kubernetes', yaml: template) {
    node ("kubernetes") {
        container("kubernetes") {
            stage ("kubernetes") {
                sh """
                  kubectl run apache --image=kaizenacademy/apache:2.0.0
                """
            }
        }
    }
}
