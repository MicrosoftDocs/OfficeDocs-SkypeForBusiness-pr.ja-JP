---
title: Skype for Business Server で会議ディレクトリを作成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: '概要: Skype for Business Server で会議ディレクトリを作成する方法について学習します。'
ms.openlocfilehash: e4d73cc73a5c3c343e8a4734923cf80fb2590211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119476"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a>Skype for Business Server で会議ディレクトリを作成する
 
**概要:** Skype for Business Server で会議ディレクトリを作成する方法について学習します。
  
会議ディレクトリは、Skype for Business を使用するときに参加者が会議に参加するために使用する英数字会議 ID と、ダイヤルイン会議参加者が会議に参加するために使用する数値専用の会議 ID との間のマッピングを維持します。 
  
## <a name="create-a-conference-directory"></a>会議ディレクトリの作成

複数の会議ディレクトリを作成すると、作成する会議の数がよほど多くならない限り電話会議 ID を短く保つことができます。 
  
ユーザーあたりの電話会議の数が一般的な組織の場合、プール内の 999 ユーザーごとに 1 つの会議ディレクトリを作成することをお勧めします。 このガイドラインを使用すると、通常、会議の ID を小さくすることができます。 ただし、(プール全体の) 会議ディレクトリの数が 9 を超えると、会議 ID の長さが増えて、追加の会議がサポートされます。
  
会議 ID の形式は次のとおりです。 
  
```console
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

会議ディレクトリを作成するには **、New-CsConferenceDirectory コマンドレットを使用** します。 たとえば、次のコマンドを実行すると、ID 42 を持つ会議ディレクトリが作成されます。このディレクトリは、次の atl-cs-001.litwareinc.com。
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

詳細については [、「New-CsConferenceDirectory」を参照してください](/powershell/module/skype/new-csconferencedirectory?view=skype-ps)。
