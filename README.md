package com.saucedemo;

import com.daniyar.configuration.reader.Config;
import com.daniyar.configuration.reader.properties.PropertiesLoader;
import com.daniyar.configuration.reader.properties.Property;
import com.daniyar.configuration.reader.properties.PropertyFile;

@PropertyFile("config.properties")
public class TestsConfig extends Config {

    private static TestsConfig config;

    public static TestsConfig getConfig() {
        if (config == null) {
            config = new TestsConfig();
        }
        return config;
    }

    public TestsConfig() {
        PropertiesLoader.populate(this);
    }

    @Property("saucedemo.url")
    private String baseUrl;

    /**
     * @return Test Object URL
     */
    public String getBaseUrl() {
        return baseUrl;
    }
}
