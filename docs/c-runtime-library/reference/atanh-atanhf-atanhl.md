---
title: "atanh, atanhf, atanhl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: ["cpp-standard-libraries"]
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: ["atanhl", "atanhf", "atanh"]
apilocation: ["msvcrt.dll", "msvcr80.dll", "msvcr90.dll", "msvcr100.dll", "msvcr100_clr0400.dll", "msvcr110.dll", "msvcr110_clr0400.dll", "msvcr120.dll", "msvcr120_clr0400.dll", "ucrtbase.dll", "api-ms-win-crt-math-l1-1-0.dll"]
apitype: "DLLExport"
f1_keywords: ["atanhl", "atanhf", "atanh"]
dev_langs: ["C++"]
helpviewer_keywords: ["atanhf function", "atanhl function", "atanh funciton"]
ms.assetid: 83a43b5b-2580-4461-854f-dc84236d9f32
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
ms.workload: ["cplusplus"]
---
# atanh, atanhf, atanhl
Calculates the inverse hyperbolic tangent.  
  
## Syntax  
  
```  
double atanh(  
   double x   
);  
float atanh(  
   float x   
);  // C++ only  
long double atanh(  
   long double x  
);  // C++ only  
float atanhf(  
   float x   
);  
long double atanhl(  
   long double x  
);  
```  
  
#### Parameters  
 `x`  
 Floating-point value.  
  
## Return Value  
 The `atanh` functions return the inverse hyberbolic tangent (arc hyperbolic tangent) of `x`. If `x` is greater than 1, or less than -1, `errno` is set to `EDOM` and the result is a quiet NaN. If `x` is equal to 1 or -1, a positive or negative infinity is returned, respectively, and `errno` is set to `ERANGE`.  
  
|Input|SEH Exception|`Matherr` Exception|  
|-----------|-------------------|-------------------------|  
|± QNAN,IND|none|none|  
|`X` ≥ 1; `x` ≤ -1|none|none|  
  
## Remarks  
 Because C++ allows overloading, you can call overloads of `atanh` that take and return `float` or `long double` values. In a C program, `atanh` always takes and returns `double`.  
  
## Requirements  
  
|Function|C header|C++ header|  
|--------------|--------------|------------------|  
|`atanh`, `atanhf`, `atanhl`|\<math.h>|\<cmath>|  
  
 For additional compatibility information, see [Compatibility](../../c-runtime-library/compatibility.md).  
  
## Example  
  
```  
// crt_atanh.c  
// This program displays the hyperbolic tangent of pi / 4  
// and the arc hyperbolic tangent of the result.  
//  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double pi = 3.1415926535;  
   double x, y;  
  
   x = tanh( pi / 4 );  
   y = atanh( x );  
   printf( "tanh( %f ) = %f\n", pi/4, x );  
   printf( "atanh( %f ) = %f\n", x, y );  
}  
```  
  
```Output  
tanh( 0.785398 ) = 0.655794  
atanh( 0.655794 ) = 0.785398  
```  
  
## See Also  
 [Floating-Point Support](../../c-runtime-library/floating-point-support.md)   
 [acos, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [asin, asinf, asinl](../../c-runtime-library/reference/asin-asinf-asinl.md)   
 [atan, atanf, atanl, atan2, atan2f, atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [sin, sinf, sinl, sinh, sinhf, sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [tan, tanf, tanl, tanh, tanhf, tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)   
 [_CItan](../../c-runtime-library/citan.md)