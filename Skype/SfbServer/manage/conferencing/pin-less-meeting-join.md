---
title: Skype for Business Server で PIN を使用する会議参加を構成する
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
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: '概要: Skype for Business Server で PIN を使用する会議参加オプションを構成する方法について学習します。'
ms.openlocfilehash: 794bf13d92857a18254f903a1c5dcca98d0a1ec0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827987"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>Skype for Business Server で PIN を使用する会議参加を構成する
 
**概要:** Skype for Business Server で PIN を使用する会議参加オプションを構成する方法について学習します。
  
ダイヤルイン発信者が会議に参加しようとすると、電話会議 自動応答 (CAA) サービスは、発表者が通話中で、ダイヤルイン発信者がリーダー PIN を入力していない場合、ロビー &#x2014; とは異なる保持ペンで発信者を配置します。 PIN なし会議参加オプションを使用すると、ダイヤルイン発信者は、通話の最初のユーザーである場合でも、リーダー PIN を入力せずに会議に参加できます。 
  
この機能を構成する場合は、次の注意が必要です。
  
- プライベート会議にのみ適用されます。
    
- PSTN 発信者は、認証されたユーザーがいなくてもプライベート会議に参加できます。
    
- 設定が変更された後は、すべての既存および新しいプライベート会議に適用されます。
    
- 開催者のサイトまたはグローバル レベルで有効にできます。
    
- ロビーをバイパスできるユーザーのオプションは、次のどちらかに設定できます。 
    
  - **組織から発信者が直接アクセスできるユーザー**
    
  - **発信者が直接アクセス** できるユーザー (制限なし) (これは既定の設定です)。
    
- PIN レス参加を有効にするように構成されている場合でも、CAA サービスは引き続きリーダー PIN の入力を求めるメッセージを表示します。 PIN が入力されている場合でも、ユーザーは会議に参加できます。 ただし、リーダー PIN を入力する機能を保持すると、ダイヤルイン発信者はリーダーとして認証し、必要に応じて会議を管理できます。
    
## <a name="configure-pin-less-meeting-join"></a>PIN を使用する会議参加を構成する

ユーザーに対して PIN 非使用の会議参加を有効にするには、次のように [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) コマンドレットを AllowAnonymousPstnActivation パラメーターと一緒に使用します。
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

たとえば、次のコマンドは、サイト Redmond に対して PIN を使用する会議参加を有効にしています。
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

セキュリティ上の目的から、PIN を使用する会議参加が有効になっている場合は、ConferencingPolicy が次のように設定された状態で匿名ユーザーのダイヤルアウトを制限できます。
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

詳細については [、「Set-CsConferencingPolicy」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
  

