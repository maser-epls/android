# Implement Senesor in Kotlin
```
import android.hardware.Sensor
import android.hardware.SensorEvent
import android.hardware.SensorEventListener
import android.hardware.SensorManager

class MainActivity : AppCompatActivity(), SensorEventListener {
    lateinit var SensorManager: SensorManager

    override fun onCreate(savedInstanceState: Bundle?) {
        SensorManager = getSystemService(SENSOR_SERVICE) as SensorManager
        
        val deviceSensors: List<Sensor> = SensorManager.getSensorList(Sensor.TYPE_ALL)
        mAccelerometer = SensorManager!!.getDefaultSensor(Sensor.TYPE_ACCELEROMETER)
        sensorManager.getDefaultSensor(Sensor.TYPE_ACCELEROMETER)?.let {
            this.accelerometer = it
        }
    }

    override fun onAccuracyChanged(sensor: Sensor?, accuracy: Int) {
    }

    override fun onSensorChanged(event: SensorEvent?) {
    }
}
```
