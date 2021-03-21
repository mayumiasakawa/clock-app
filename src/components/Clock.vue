<script>
  const zeroPadding = (num, digit) => {
    const zeros = digit - num.toString().length
    return '0'.repeat(zeros) + num
  }
  
  export default {
    data() {
      return {
        date: new Date(),
      }
    },
    computed: {
      year() {
        return this.date.getFullYear();
      },
      month(){
        return zeroPadding(this.date.getMonth() + 1, 2)
      },
      day(){
        return zeoPadding(this.date.getDate(), 2)
      },
      hours(){
        return zeroPadding(this.date.getHouers(), 2)
      },
      minutes(){
        return zeroPadding(this.date.getMinutes(),2)
      },
      seconds(){
        return zeroPadding(this.date.seconds(),2)
      },
    },
    mounted(){
        this.setDate()
        setInterval(() => this.setDate(), 1000)
      },
      methods: {
        setDate(){
          this.date = new Date()
        },
      },
  }
</script>