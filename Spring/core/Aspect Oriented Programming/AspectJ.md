### 1-2-2. AspectJ

AOP를 제대로 사용하기 위해 꼭 필요한 라이브러리임.

기본적으로 지원하는 Spring AOP로는 다양한 기법(pointcut 등)의 AOP를 사용할 수 없음.

---

**Aspect**

다음과 같이 Aspect를 생성함.

```java
import org.aspectj.lang.annotation.Aspcet;

@Aspect
@Component //해당 Aspect를 스프링 Bean으로 등록해서 사용하기 위함.
public class UsefulAspect {
}
```

---

**Pointcut**

다음과 같이 Pointcut을 선언함.

```java
public class UsefulAspect {
	@Pointcut("execution(* transfer(..))") //포인트 컷 표현식 
	private void anyOldTransfer() {}
}
```

> 👉🏻 해당 Aspect의 Advice가 적용될 Join point를 찾기 위한 패턴 또는 조건 생성.


다음과 같이 Pointcut을 결합할 수 있음.

```java
public class UsefulAspect {
	@Pointcut("execution(public * *(..)") //public 메소드 대상 포인트 컷
	private void anyPublicOperation() {}

	@Pointcut("within(com.xyz.myapp.tranding..*)") //특정 패키지 대상 포인트 컷
	private void inTranding() {}

	@Pointcut("anyPublicOperation() && inTranding()") //and(&&) 조건으로 결합한 포인트 컷
	private void trandingOperation() {}
}
```

---

**Advice**

다음과 같이 Pointcut 바로 전에 메소드를 실행할 수 있음.

```java
import org.aspectj.lang.annotation.Aspect;
import org.aspectj.lang.annotation.Before;

@Aspect
public class BeforeExample {
	@Before("com.xyz.myapp.CommonPointcuts.dataAccesOperation()")
	public void doAccessCheck() {
	}
}
```

다음과 같이 미리 정의된 Pointcut에서 return이 발생된 후 메소드를 실행할 수 있음.

```java
import org.aspectj.lang.annotation.Aspect;
import org.aspectj.lang.annotation.AfterReturning;

@Aspect
public class AfterReturningExample {
	@AfterReturning("com.xyz.myapp.CommonPointcuts.dataAccesOperation()")
	public void doAccessCheck() {
	}
}
```

다음과 같이 Pointcut 전/후에 필요한 동작을 추가할 수 있음.

```java
import org.aspectj.lang.annotation.Aspect;
import org.aspectj.lang.annotation.Around;
import org.aspectj.lang.ProceedingJoinPoint;

@Aspect
public class AroundExample {
	@Around("com.xyz.myapp.CommonPointcuts.businessService()")
	public Object doBasicProfiling(ProceedingJoinPint pjp) throws Throwable {
		//start stopwatch
		Object retVal = pjp.proceed();
		//stop stopwatch
		return retVal
	}
}
```