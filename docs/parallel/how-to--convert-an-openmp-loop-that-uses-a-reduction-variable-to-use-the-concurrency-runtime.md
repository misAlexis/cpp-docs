---
title: "How to: Convert an OpenMP Loop that Uses a Reduction Variable to Use the Concurrency Runtime"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "converting from OpenMP to the Concurrency Runtime, reduction variables"
  - "reduction variables, converting from OpenMP to the Concurrency Runtime"
ms.assetid: 96623f36-5e57-4d3f-8c13-669e6cd535b1
caps.latest.revision: 10
ms.author: "mithom"
manager: "ghogen"
translation.priority.ht: 
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "ru-ru"
  - "zh-cn"
  - "zh-tw"
translation.priority.mt: 
  - "cs-cz"
  - "pl-pl"
  - "pt-br"
  - "tr-tr"
---
# How to: Convert an OpenMP Loop that Uses a Reduction Variable to Use the Concurrency Runtime
This example demonstrates how to convert an OpenMP [parallel](../parallel/parallel.md)[for](../parallel/for--openmp-.md) loop that uses the [reduction](../parallel/reduction.md) clause to use the Concurrency Runtime.  
  
 The OpenMP `reduction` clause lets you specify one or more thread-private variables that are subject to a reduction operation at the end of the parallel region. OpenMP predefines a set of reduction operators. Each reduction variable must be a scalar (for example, `int`, `long`, and `float`). OpenMP also defines several restrictions on how reduction variables are used in a parallel region.  
  
 The Parallel Patterns Library (PPL) provides the [concurrency::combinable](../parallel/combinable-class.md) class, which provides reusable, thread-local storage that lets you perform fine-grained computations and then merge those computations into a final result. The `combinable` class is a template that acts on both scalar and complex types. To use the `combinable` class, perform sub-computations in the body of a parallel construct and then call the [concurrency::combinable::combine](../Topic/combinable::combine%20Method.md) or [concurrency::combinable::combine_each](../Topic/combinable::combine_each%20Method.md) method to produce the final result. The `combine` and `combine_each` methods each take a *combine function* that specifies how to combine each pair of elements. Therefore, the `combinable` class is not restricted to a fixed set of reduction operators.  
  
## Example  
 This example uses both OpenMP and the Concurrency Runtime to compute the sum of the first 35 Fibonacci numbers.  
  
 [!code[concrt-openmp#7](../parallel/codesnippet/CPP/how-to--convert-an-openmp-loop-that-uses-a-reduction-variable-to-use-the-concurrency-runtime_1.cpp)]  
  
 This example produces the following output.  
  
 **Using OpenMP...**  
**The sum of the first 35 Fibonacci numbers is 14930351.**  
**Using the Concurrency Runtime...**  
**The sum of the first 35 Fibonacci numbers is 14930351.** For more information about the `combinable` class, see [Parallel Containers and Objects](../parallel/parallel-containers-and-objects.md).  
  
## Compiling the Code  
 Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `concrt-omp-fibonacci-reduction.cpp` and then run the following command in a Visual Studio Command Prompt window.  
  
 **cl.exe /EHsc /openmp concrt-omp-fibonacci-reduction.cpp**  
  
## See Also  
 [Migrating from OpenMP to the Concurrency Runtime](../parallel/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [Parallel Containers and Objects](../parallel/parallel-containers-and-objects.md)