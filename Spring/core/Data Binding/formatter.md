### 1-4-2. Formatter

특정 객체 → String 간의 변환을 담당함.

응답을 할 때도 활용함.

```java
package org.springframework.format.datetime;

public final class DateFormatter implements Formatter<Date> {
	public String print(Date date, Locale locale) {
		return getDateFormat(locale).format(date);
	}

	public Date parse(String foamtted, Locale locale) throws ParseException {
		return getDateFormat(locale).parse(formatted);
	}

	//getDateFormat 등 일부 구현 생략
}
```

> 👉🏻 Formatter도 Converter와 마찬가지로 Spring Bean으로 등록하면 자동으로 ConversionService에 등록시켜줌.