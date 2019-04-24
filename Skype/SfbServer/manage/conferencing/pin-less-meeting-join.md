---
title: Skype for Business Server に PIN 非使用の会議参加を構成する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: '概要: レス暗証番号 (pin) を構成する方法を説明する会議のビジネス サーバーの Skype に参加するオプションです。'
ms.openlocfilehash: 4ea20f68b123f6593c5a98fc82dbca62f90f31b1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198268"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>Skype for Business Server に PIN 非使用の会議参加を構成する
 
**の概要:** レス暗証番号 (pin) を構成する方法については会議のビジネス サーバーの Skype に参加するオプション。
  
ダイヤルインの呼び出し元が会議に参加しようとすると、会議自動応答 (CAA) サービス、呼び出し側ロビー & #x 2014; とは異なる保持のペンで発表者がいない場合は、呼び出しとダイヤルインの呼び出し元の引出線の暗証番号 (pin) に入っていません。 PIN 非使用の会議参加オプションでは、ダイヤル イン発信者が最初の通話ユーザーであっても主催者 PIN を入力することなく会議に参加できます。 
  
この機能を構成する場合は、次の点に注意してください。
  
- プライベート会議にのみ適用されます。
    
- 認証ユーザーが存在しなくても PSTN 発信者がプライベート会議に留まることができます。
    
- 設定の変更後、既存のすべてのプライベート会議と新しいプライベート会議に適用されます。
    
- 開催者のサイトまたはグローバル レベルで有効にできます。
    
- ロビーをバイパスするユーザーのオプションは、次のいずれかに設定できます。 
    
  - **組織内の誰でも、発信者が直接参加する**
    
  - **誰でも (制限なし)、発信者が直接参加する** (これは既定の設定です)。
    
- PIN 非使用の参加を有効に構成した場合でも、CAA サービスでは主催者 PIN のプロンプトが表示されます。 ユーザーは、PIN の入力にかかわらず、会議に参加できます。 ただし、引出線の暗証番号 (pin) を入力する機能を維持したままリーダーとして認証し、必要に応じて会議を管理するのにはダイヤルインの呼び出し元を使用できます。
    
## <a name="configure-pin-less-meeting-join"></a>PIN 非使用の会議参加の構成

ユーザーの暗証番号 (pin) のない会議の参加を有効にするには、次のように AllowAnonymousPstnActivation パラメーターを使用して[セット CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)コマンドレットを使用します。
  
```
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

たとえば、次のコマンドによって、サイト Redmond に対して PIN 非使用の会議参加を有効にします。
  
```
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

PIN 非使用の会議参加を有効にした場合、セキュリティ上の理由から、ConferencingPolicy を以下のように設定することにより、匿名ユーザーのダイヤル発信を制限することをお勧めします。
  
```
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

詳細については、[セット CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)を参照してください。
  

