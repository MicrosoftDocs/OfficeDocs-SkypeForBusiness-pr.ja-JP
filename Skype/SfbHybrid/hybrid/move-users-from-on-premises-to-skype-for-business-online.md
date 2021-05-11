---
title: ユーザーをオンプレミスから Skype for Business Online に移動する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: ユーザーをオンラインに移動するSkype for Businessします。
ms.openlocfilehash: e4536b13b6a9c05757bfcbf629fcc8301f94ed86
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305981"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>ユーザーをオンプレミスから Skype for Business Online に移動する

オンプレミスからオンラインにユーザーを移動した後Skype for Businessユーザーは、その機能のために Skype for Business Online を操作します。 オンプレミスに存在していた連絡先は Skype for Business Online で利用できます。また、ユーザーが将来開催する既存の会議は更新され、リンクは Skype for Business Online を指します。 ユーザーが電話会議を有効にしている場合、会議にはダイヤルイン座標も含まれます。  ユーザーをオンプレミス環境から Skype for Business Online に移動するには、Move-CsUser コマンドレットまたは Skype for Business Server コントロール パネルのいずれかを使用します。どちらもオンプレミス ツールです。 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

ユーザーを移動する前に、必ず前提条件を確認 [して](move-users-between-on-premises-and-cloud.md#prerequisites) 、ユーザーをクラウドに移動してください。

> [!NOTE]
> Skype for Business Online の今後の退職に備えて、Microsoft は近い将来、組織が Teams に移行する方法を簡素化し、Skype for Business Online に移行できなくなりました。  これらの変更を利用できると、ユーザーをオンプレミスからクラウドに移動すると、ユーザーには TeamsOnly モードが自動的に割り当て、スイッチが実際に指定されたかどうかに関係なく、スイッチが指定された場合と同様に、ユーザーの会議が自動的に Teams 会議に変換されます。 `-MoveToTeams` この機能は、2021 年 7 月 31 日の実際の使用が解除される前にリリースされる予定です。   現在、このスイッチを指定しない場合、ユーザーは Skype for Business Server オンプレミスのホームから Skype for Business Online に移行し、モードは変更されず、この記事に記載されている機能です。

 
## <a name="move-users-with-move-csuser"></a>ユーザーをユーザーに移動Move-CsUser 

Move-CsUser管理シェル PowerShell ウィンドウからSkype for Business使用できます。 「必須の管理資格情報」の説明に従って、オンプレミス環境と組織の両方で十分Microsoft 365[必要があります](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。 両方の環境で特権を持つ 1 つのアカウントを使用するか、オンプレミスの資格情報を使用してオンプレミスの Skype for Business Server 管理シェル ウィンドウを起動し、パラメーターを使用して、必要な管理役割を持つ Microsoft 365 アカウントの資格情報を指定できます。 `-Credential`

Move-CsUser を使用してユーザーをオンラインに移動するには、次のコマンドを実行します。

- Identity パラメーターを使用して移動するユーザーを指定します。
- 値 "sipfed.online.lync" で -Target パラメーターを指定します。 <span>com」
- オンプレミスと Microsoft 365 の両方で十分なアクセス許可を持つアカウントが 1 つない場合は、-credential パラメーターを使用して、Microsoft 365 で十分なアクセス許可を持つアカウントを指定します。
- アクセス許可が設定されているアカウントMicrosoft 365.onmicrosoft で終了しない場合。 <span>com"の場合は、-HostedMigrationOverrideUrl パラメーターを指定し、「必須の管理資格情報」の説明に従って正しい値[を指定する必要があります](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。

次のコマンドレット シーケンスを使用して、ユーザーを Online に移動Skype for Businessできます。 この資格情報は、Microsoft 365アカウントであり、ユーザープロンプトの入力として提供Get-Credentialします。

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

管理者アカウントが MFA (多要素認証) が有効になっている場合は、-Credential パラメーターを指定しません。 管理者に資格情報の入力を求めるメッセージが表示されます。

## <a name="move-users-with-skype-for-business-server-control-panel"></a>コントロール パネルでユーザー Skype for Business Server移動する 

1. コントロール パネル アプリSkype for Business Server開きます。
2. 左側のナビゲーションで、[ユーザー] を **選択します**。
3. [**検索]** を使用して、[オンライン] に移動するユーザーをSkype for Businessします。
4. ユーザーを選択し、リストの上にある [アクション] ドロップダウンから 、[選択したユーザーをオンラインに移動Skype for Business **します**。
5. ウィザードで、[ **次へ**] をクリックします。
6. メッセージが表示されたら、.Microsoft 365で終わり、十分なアクセス許可を持つアカウントを使用して、onmicrosoft.com にサインインします。
7. [ **次へ]** をクリックし、[ **次** へ] をクリックしてもう 1 回ユーザーを移動します。
8. 成功または失敗に関する状態メッセージは、ウィザードではなく、メインのコントロール パネル アプリの上部に表示されます。

## <a name="see-also"></a>関連項目

[Move-CsUser](/powershell/module/skype/move-csuser)
