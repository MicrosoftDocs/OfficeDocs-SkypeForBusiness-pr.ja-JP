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
description: ユーザーを Skype for Business Online に移動する方法について説明します。
ms.openlocfilehash: a9fb80046195580daca6dfc7f810b2e0c1877f1c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221117"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>ユーザーをオンプレミスから Skype for Business Online に移動する

オンプレミスから Skype for Business Online にユーザーを移動すると、ユーザーは Skype for Business Online と対話してその機能を利用できるようになります。 オンプレミスに存在していた連絡先は、Skype for business Online で利用できるようになります。また、今後、ユーザーが開催した既存の会議が更新されるようになっています。このリンクは、Skype for Business Online を指すようになります。 ユーザーが電話会議に対して有効になっている場合、会議にはダイヤルイン座標も含まれます。  オンプレミス環境から Skype for Business Online にユーザーを移動するには、ユーザーコマンドレットを使用するか、または Skype for Business Server コントロールパネルを使用します。どちらもオンプレミスのツールです。 

ユーザーを移動する前に、ユーザーをクラウドに移動するための[前提条件](move-users-between-on-premises-and-cloud.md#prerequisites)を確認してください。
 
## <a name="move-users-with-move-csuser"></a>Move-CsUser を使用してユーザーを移動する 

Move-CsUser は、オンプレミスの Skype for Business 管理シェル PowerShell ウィンドウから入手できます。 [必要な管理者の資格情報](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)に説明されているように、オンプレミス環境と Microsoft 365/Office 365 組織の両方に十分な特権を持っている必要があります。 両方の環境で権限を持つ単一のアカウントを使用するか、オンプレミスの資格情報を使用してオンプレミスの Skype for Business Server 管理シェルウィンドウを開始することができます。また、パラメーターを使用して、 `-Credential` 必要な管理役割を持つ Microsoft 365 または Office 365 アカウントの資格情報を指定することもできます。

ユーザーを Move-CsUser を使用してオンラインに移行するには、次のようにします。

- Identity パラメーターを使用して移動するユーザーを指定します。
- 値が "sipfed <span> " の-Target パラメーターを指定します。com "。
- オンプレミスと Office 365 の両方に十分な権限を持つアカウントがない場合は、-credential パラメーターを使用して、Office 365 に十分なアクセス許可を持つアカウントを指定します。
- Office 365 のアクセス許可を持つアカウントが "onmicrosoft <span> " で終了していない場合。com の場合は、-HostedMigrationOverrideUrl パラメーターを指定する必要があります。詳細については、「[必要な管理者の資格情報](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)」を参照してください。

次のコマンドレットシーケンスを使用して、ユーザーを Skype for Business Online に移動できます。 この例では、Microsoft 365 または Office 365 の資格情報が別のアカウントであり、資格情報の取得を求めるプロンプトの入力として指定されています。

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

管理者アカウントが MFA (多要素認証) を有効にしている場合は、-Credential パラメーターを指定しないでください。 管理者は資格情報の入力を求められます。

## <a name="move-users-with-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用してユーザーを移動する 

1. Skype for Business Server コントロールパネルアプリを開きます。
2. 左側のナビゲーションで、[**ユーザー**] を選択します。
3. [**検索**] を使用して、Skype For business Online に移動するユーザーを検索します。
4. ユーザーを選択し、リストの上にある**アクション**ドロップダウンから、[**選択されたユーザーを Skype for Business Online に移動**] を選択します。
5. ウィザードで、[ **次へ**] をクリックします。
6. メッセージが表示された場合は、onmicrosoft.com で終了し、十分な権限があるアカウントを使用して、Microsoft 365 または Office 365 にサインインします。
7. [**次へ**] をクリックし、[**次**へ] をもう一度クリックして、ユーザーを移動します。
8. 成功または失敗に関するステータスメッセージは、ウィザードではなく、メインコントロールパネルアプリの上部に表示されることに注意してください。

## <a name="see-also"></a>関連項目

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
