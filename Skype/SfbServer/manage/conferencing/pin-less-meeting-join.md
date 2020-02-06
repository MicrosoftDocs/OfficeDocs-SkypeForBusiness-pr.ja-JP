---
title: Skype for Business Server に PIN 非使用の会議参加を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: '概要: Skype for Business Server で PIN を使用しない会議の参加オプションを構成する方法について説明します。'
ms.openlocfilehash: a52738f2ca679838ab7687cde2c017e3364542a7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818488"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>Skype for Business Server に PIN 非使用の会議参加を構成する
 
**概要:** Skype for Business Server で PIN を使用しない会議の参加オプションを構成する方法について説明します。
  
ダイヤルインの発信者が会議に参加しようとすると、会議の自動応答 (CAA を) サービスは、発表者が通話を開始していない場合や、ダイヤルインの発信者がリーダーの PIN を入力していない場合に、ロビー &#x2014; とは異なるホールディングペンに発信者を配置します。 PIN 非使用の会議参加オプションでは、ダイヤル イン発信者が最初の通話ユーザーであっても主催者 PIN を入力することなく会議に参加できます。 
  
この機能を構成する場合は、次の点に注意してください。
  
- プライベート会議にのみ適用されます。
    
- 認証ユーザーが存在しなくても PSTN 発信者がプライベート会議に留まることができます。
    
- 設定の変更後、既存のすべてのプライベート会議と新しいプライベート会議に適用されます。
    
- 開催者のサイトまたはグローバル レベルで有効にできます。
    
- ロビーをバイパスするユーザーのオプションは、次のいずれかに設定できます。 
    
  - **組織内の誰でも、発信者が直接参加する**
    
  - **誰でも (制限なし)、発信者が直接参加する** (これは既定の設定です)。
    
- PIN 非使用の参加を有効に構成した場合でも、CAA サービスでは主催者 PIN のプロンプトが表示されます。 ユーザーは、PIN の入力にかかわらず、会議に参加できます。 ただし、リーダー PIN を入力する機能を維持すると、ダイヤルインの発信者はリーダーとして認証し、必要に応じて会議を管理することができます。
    
## <a name="configure-pin-less-meeting-join"></a>PIN 非使用の会議参加の構成

ユーザーに対して PIN を使用しない会議の参加を有効にするには、次のように AllowAnonymousPstnActivation パラメーターを指定して[CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)コマンドレットを使用します。
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

たとえば、次のコマンドによって、サイト Redmond に対して PIN 非使用の会議参加を有効にします。
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

PIN 非使用の会議参加を有効にした場合、セキュリティ上の理由から、ConferencingPolicy を以下のように設定することにより、匿名ユーザーのダイヤル発信を制限することをお勧めします。
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

詳細については、「 [Set-set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)」を参照してください。
  

