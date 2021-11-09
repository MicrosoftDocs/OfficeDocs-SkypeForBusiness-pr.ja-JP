---
title: 会議の PIN レス会議参加を構成Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: '概要: 会議で PIN レス会議参加オプションを構成する方法についてSkype for Business Server。'
ms.openlocfilehash: 13af671edaa9ab8853e0390d43c62b6576bed4e2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861364"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>会議の PIN レス会議参加を構成Skype for Business Server
 
**概要:** PIN レス会議参加オプションを構成する方法については、Skype for Business Server。
  
ダイヤルイン発信者が会議に参加しようとすると、会議 自動応答 (CAA) サービスは、発表者が通話中で、ダイヤルイン発信者がリーダー PIN を入力していない場合、ロビー &#x2014; とは異なる保持ペンに発信者を配置します。 PIN なしの会議参加オプションを使用すると、通話の最初のユーザーである場合でも、ダイヤルイン発信者はリーダー PIN を入力せずに会議に参加できます。 
  
この機能を構成する場合は、次の注意が必要です。
  
- プライベート会議にのみ適用されます。
    
- PSTN 発信者は、認証されたユーザーが存在せずにプライベート会議に参加できます。
    
- 設定が変更された後は、既存の会議と新しいプライベート会議に適用されます。
    
- 開催者のサイトまたはグローバル レベルで有効にできます。
    
- ロビーをバイパスできるユーザーのオプションは、次のどちらかに設定できます。 
    
  - **発信者が所属する組織のユーザーが直接アクセスする**
    
  - **発信者が直接アクセスするユーザー** (制限なし) (これは既定の設定です)。
    
- PIN レス参加を有効にするように構成されている場合でも、CAA サービスは引き続きリーダー PIN の入力を求めるメッセージを表示します。 ユーザーは、PIN を入力したかどうかに関して会議に参加できます。 ただし、リーダー PIN を入力する機能を保持すると、ダイヤルイン発信者はリーダーとして認証し、必要に応じて会議を管理できます。
    
## <a name="configure-pin-less-meeting-join"></a>PIN レス会議参加の構成

ユーザーの PIN レス会議参加を有効にするには [、Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) コマンドレットと AllowAnonymousPstnActivation パラメーターを次のように使用します。
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

たとえば、次のコマンドは、サイト Redmond の PIN レス会議参加を有効にしています。
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

セキュリティ上の目的で、PIN レス会議参加が有効になっている場合は、MeetingingPolicy が次のように設定された状態で匿名ユーザーのダイヤルアウトを制限できます。
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

詳細については [、「Set-CsConferencingPolicy」を参照してください](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
