---
title: ビジネス サーバーのため、Skype で会議ディレクトリを作成します。
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: '概要: は、Skype のビジネス サーバーの会議ディレクトリを作成する方法を説明します。'
ms.openlocfilehash: 9e79ca7e1b2f896746db998cc53983c04c6724ef
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883515"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a>ビジネス サーバーのため、Skype で会議ディレクトリを作成します。
 
**の概要:** ビジネス サーバーの Skype での会議ディレクトリを作成する方法について説明します。
  
会議ディレクトリは、ビジネス用の Skype を使用する場合、会議に参加する参加者が使用する英数字のミーティング ID と、ダイヤルイン会議の参加者が会議に参加するのには使用する数値のみの会議 ID 間のマッピングを維持します。 
  
## <a name="create-a-conference-directory"></a>電話会議ディレクトリを作成する

複数の電話会議ディレクトリを作成すると、作成する電話会議の数がよほど多くならない限り、電話会議 ID を短く保つことができます。 
  
ユーザーあたりの電話会議の数が標準的である組織の場合は、プール内の 999 ユーザーごとに 1 つの電話会議ディレクトリを作成することをお勧めします。このガイドラインを使用すると、一般に電話会議 ID が短く保たれます。ただし、(すべてのプールでの) 電話会議ディレクトリの数が 9 よりも多くなると、会議 ID の長さは、追加の電話会議に対応して長くなります。
  
電話会議 ID の形式は次のとおりです。 
  
```
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

電話会議ディレクトリを作成するには、**New-CsConferenceDirectory** コマンドレットを使用します。たとえば、以下では、ID が 42 で、プール atl-cs-001.litwareinc.com でホストされる電話会議ディレクトリが作成されます。
  
```
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

詳細については、[新規 CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps)を参照してください。
  

