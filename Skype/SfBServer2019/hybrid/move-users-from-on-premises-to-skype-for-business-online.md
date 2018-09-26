---
title: ユーザーをオンプレミスから Skype for Business Online に移動する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: '概要: は、ユーザー設定を移行し、オンライン ビジネスの Skype ユーザーを移動する方法を説明します。'
ms.openlocfilehash: 9fd51c55be35e55be6ca837ccb72413043283ac7
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "25030750"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>ユーザーをオンプレミスから Skype for Business Online に移動する

**の概要:** ユーザー設定を移行し、オンライン ビジネスの Skype ユーザーを移動する方法について説明します。

Office 365 にユーザーを実際に移動するには、前に、ユーザー アカウントは、クラウドに同期され、ライセンスを割り当てることを確認する必要があります。 この操作には、Office 365 管理センターを使用します。

### <a name="to-confirm-that-an-on-premises-user-account-has-been-synchronized-with-office-365"></a>オンプレミス ユーザー アカウントが Office 365 と同期していることを確認するには

1. テナント管理者のアカウントを使用して、テナントの Office 365 の管理ページを開きます。  テナント管理者のアカウントは、Office 365 でこの機能を実行するのにはビジネス管理者の役割とユーザー管理の役割 (または、グローバル管理者ロール) の両方の Skype に付与してください。

2. 左側のナビゲーション ウィンドウで、[**ユーザー**] をクリックし、[**アクティブ ユーザ**] をクリックします。

3. [**ユーザーの検索**] をクリックして、ユーザーの名前を入力します。

4. ユーザーを参照してください、それらの状態が**Active Directory に Synched**を確認します。

    ユーザーがまだ同期されていない場合は、3 時間以内に次の自動同期が実行されます。 早く同期を強制的にすることもできます。 詳細については、[ディレクトリ同期の強制](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx)を参照してください。

Office 365 のライセンスを割り当てるには、[ビジネス向けの Office 365 のユーザーにライセンスを割り当てる](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc)を参照してください。

## <a name="migrate-user-settings-to-skype-for-business-online"></a>Skype をオンライン ビジネスのユーザー設定を移行します。

Skype をビジネス オンラインのユーザーを移行する前に移動するアカウントに関連付けられたユーザー データをバックアップしてください。 ユーザー アカウントと共にすべてのユーザー データが移動されるわけではありません。 についてを参照してください[のバックアップと復元の要件: データ](https://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx)。

ユーザー設定は、ユーザー アカウントと共に移動されます。いくつかのオンプレミス設定は、ユーザー アカウントと共に移動されることはありません。

## <a name="move-pilot-users-to-skype-for-business-online"></a>ビジネス オンラインの Skype をパイロット ユーザーの移動

Skype をビジネス オンラインのユーザーを移動する前に、環境が正しく構成されていることを確認するのには、いくつかのパイロット ユーザーを移動することがあります。 その他のユーザーを移動する前に、機能とサービス機能が予想どおりであることを確認できます。

オンライン ビジネスのテナントの Skype に、オンプレミスのユーザーを移動するには、ビジネス サーバー管理シェルを管理者の資格情報を使用して、Microsoft Office 365 のテナントのため、Skype で次のコマンドレットを実行します。 "Username@contoso.com"を移動したいユーザーの情報に置き換えます。

```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds
```

## <a name="move-users-to-skype-for-business-online"></a>Skype for Business Online にユーザーを移動する

[Get CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)コマンドレットを使用して複数のユーザーを移動することができます、RegistrarPool などのユーザー アカウントに割り当てられている特定のプロパティを使用してユーザーを選択するフィルター パラメーターを使用します。 コマンドレットにパイプ[移動 CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps)コマンドレットでは、返されるユーザーは、次の例に示すように。

```
Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds
```

次の例に示すように、指定した OU 内のすべてのユーザーを取得するために OU パラメーターを使用できます。

```
Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds
```

## <a name="verify-online-user-settings-and-features"></a>オンライン ユーザーの設定と機能を確認する

ユーザーの移動が正常に完了したことは、次の方法で確認できます。

- Skype for Business Online コントロール パネルでユーザーの状態を表示します。オンプレミス ユーザーとオンライン ユーザーでは視覚的なインジケーターが異なります。

- 次のコマンドレットを実行します。

  ```
  Get-CsUser -Identity
  ```


