---
title: Skype for Business Server で会議ディレクトリを作成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: '概要: Skype for Business Server で会議ディレクトリを作成する方法について説明します。'
ms.openlocfilehash: 0ed141b743d436ca2082b8a4f5010011a0256479
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991852"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a>Skype for Business Server で会議ディレクトリを作成する
 
**概要:** Skype for Business Server で会議ディレクトリを作成する方法について説明します。
  
会議ディレクトリは、Skype for Business を使用しているときに参加者が会議に参加するために使用する英数字の会議 ID と、ダイヤルイン会議の参加者が会議に参加するために使用する電話番号のみの会議 id の間のマッピングを維持します。 
  
## <a name="create-a-conference-directory"></a>電話会議ディレクトリを作成する

複数の電話会議ディレクトリを作成すると、作成する電話会議の数がよほど多くならない限り、電話会議 ID を短く保つことができます。 
  
ユーザーあたりの電話会議の数が標準的である組織の場合は、プール内の 999 ユーザーごとに 1 つの電話会議ディレクトリを作成することをお勧めします。このガイドラインを使用すると、一般に電話会議 ID が短く保たれます。ただし、(すべてのプールでの) 電話会議ディレクトリの数が 9 よりも多くなると、会議 ID の長さは、追加の電話会議に対応して長くなります。
  
電話会議 ID の形式は次のとおりです。 
  
```
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

電話会議ディレクトリを作成するには、**New-CsConferenceDirectory** コマンドレットを使用します。たとえば、以下では、ID が 42 で、プール atl-cs-001.litwareinc.com でホストされる電話会議ディレクトリが作成されます。
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

詳細については、「 [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps)」を参照してください。
  

