# Implement Senesor in Kotlin
```
import android.hardware.Sensor
import android.hardware.SensorEvent
import android.hardware.SensorEventListener
import android.hardware.SensorManager
import XXX

class XXX : XXX, SensorEventListener {
    lateinit var mSensorManager: SensorManager

    override fun onCreate(savedInstanceState: Bundle?) {
        mSensorManager = getSystemService(SENSOR_SERVICE) as SensorManager
        
        <<Register Sensor.TYPE_MAGNETIC_FIELD >>
        mSensorManager.registerListener(mySensorEventListener, mSensorManager.getDefaultSensor(Sensor.TYPE_MAGNETIC_FIELD),SensorManager.SENSOR_DELAY_NORMAL);
        
        <<Get sensor list>>
        val deviceSensors: List<Sensor> = SensorManager.getSensorList(Sensor.TYPE_ALL)
        
    }
    
    private val mySensorEventListener: SensorEventListener = object : SensorEventListener {
        override fun onAccuracyChanged(sensor: Sensor?, accuracy: Int) {
        }
        override fun onSensorChanged(event: SensorEvent?) {
        switch (event.sensor.getType()) {
            case Sensor.TYPE_MAGNETIC_FIELD:
                mags = event.values.clone();
                break;
            case Sensor.TYPE_ACCELEROMETER:
                accels = event.values.clone();
                break;
         
        }
        
        <<some condition to get data...>>
    }
    

}
```
