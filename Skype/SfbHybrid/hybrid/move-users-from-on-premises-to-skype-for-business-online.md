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
ms.openlocfilehash: 8c028044fe8c4b808a419503091f9ecf767cfe4d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237963"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>ユーザーをオンプレミスから Skype for Business Online に移動する

オンプレミスからオンラインにユーザーを移動した後Skype for Businessユーザーは、その機能のために Skype for Business Online を操作します。 オンプレミスに存在していた連絡先は Skype for Business Online で利用できます。また、ユーザーが将来開催する既存の会議は更新され、リンクは Skype for Business Online を指します。 ユーザーが電話会議を有効にしている場合、会議にはダイヤルイン座標も含まれます。  ユーザーをオンプレミス環境から Skype for Business Online に移動するには、Move-CsUser コマンドレットまたは Skype for Business Server コントロール パネルのいずれかを使用します。どちらもオンプレミス ツールです。 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

ユーザーを移動する前に、必ず前提条件を確認 [して](move-users-between-on-premises-and-cloud.md#prerequisites) 、ユーザーをクラウドに移動してください。
 
## <a name="move-users-with-move-csuser"></a>ユーザーをユーザーに移動Move-CsUser 

Move-CsUser管理シェル PowerShell ウィンドウからSkype for Business使用できます。 「必須の管理資格情報」の説明に従って、オンプレミス環境と Microsoft 365/Office 365 組織の両方で十分な特権を持っている[必要があります](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。 両方の環境で特権を持つ 1 つのアカウントを使用するか、オンプレミスの資格情報を使用してオンプレミスの Skype for Business Server 管理シェル ウィンドウを起動し、パラメーターを使用して、必要な管理役割を持つ Microsoft 365 アカウントまたは Office 365 アカウントの資格情報を指定できます。 `-Credential`

Move-CsUser を使用してユーザーをオンラインに移動するには、次のコマンドを実行します。

- Identity パラメーターを使用して移動するユーザーを指定します。
- 値 "sipfed.online.lync" で -Target パラメーターを指定します。 <span>com」
- オンプレミスと Office 365 の両方で十分なアクセス許可を持つアカウントが 1 つない場合は、-credential パラメーターを使用して、Office 365 で十分なアクセス許可を持つアカウントを指定します。
- アカウントにアクセス許可を持つアカウントOffice 365.onmicrosoft で終了しない場合。 <span>com"の場合は、-HostedMigrationOverrideUrl パラメーターを指定し、「必須の管理資格情報」の説明に従って正しい値[を指定する必要があります](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。

次のコマンドレット シーケンスを使用して、ユーザーを Online に移動Skype for Businessできます。 この資格情報は、Microsoft 365またはOffice 365資格情報が別のアカウントであり、ユーザープロンプトの入力としてGet-Credentialします。

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
6. メッセージが表示されたら、.Microsoft 365でOffice 365で、十分なアクセス許可を持つアカウントを使用して、Microsoft 365 または onmicrosoft.com にサインインします。
7. [ **次へ]** をクリックし、[ **次** へ] をクリックしてもう 1 回ユーザーを移動します。
8. 成功または失敗に関する状態メッセージは、ウィザードではなく、メインのコントロール パネル アプリの上部に表示されます。

## <a name="see-also"></a>こちらもご覧ください

[Move-CsUser](/powershell/module/skype/move-csuser)