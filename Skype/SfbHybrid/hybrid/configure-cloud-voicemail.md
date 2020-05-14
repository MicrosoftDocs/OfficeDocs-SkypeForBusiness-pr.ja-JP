---
title: オンプレミスのユーザー用にクラウドボイスメールサービスを構成する
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Skype for Business Server を使用しているユーザーに対して、クラウドベースのボイスメールを実装する方法について説明します。
ms.openlocfilehash: 8284ee3d06574f3d5772b929fcae8363f399acb8
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221461"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a>オンプレミスのユーザー用にクラウドボイスメールサービスを構成する

## <a name="overview"></a>概要 
この記事では、Skype for Business オンプレミスユーザー用に Microsoft クラウドボイスメールサービスを構成する方法について説明します。  

この記事では、サポートされているトポロジで Skype for Business Server が既に展開されており、ハイブリッド接続をセットアップするための前提条件を満たしていることを前提としています。

クラウドボイスメールを実装する場合の利点、計画に関する考慮事項、および要件の詳細については、「 [Plan Cloud ボイスメールサービス](plan-cloud-voicemail.md)」を参照してください。




クラウドボイスメールの構成には、次のタスクが含まれます。

1.  「 [Plan Cloud ボイスメールサービス](plan-cloud-voicemail.md)」で説明されている前提条件を満たしていることを確認します。

2.  「ハイブリッド[接続を計画](plan-hybrid-connectivity.md)する」および「[ハイブリッド接続を構成](configure-hybrid-connectivity.md)する」の説明に従って、ハイブリッド接続を設定していることを確認してください。 

3.  この記事で説明されているよう[に、エッジサーバーのホスティングプロバイダーとして Cloud 留守番電話を構成](#configure-cloud-voicemail-as-the-hosting-provider)します。

4.  この記事で説明されているように[、ホスト型ボイスメールポリシーを構成](#configure-a-hosted-voicemail-policy)します。

5.  この記事で説明されているように[、ホスト型ボイスメールポリシーを割り当て](#assign-a-hosted-voicemail-policy)ます。

6.  この記事で説明されているよう[に、ユーザーのクラウドボイスメールを有効に](#enable-a-user-for-cloud-voicemail)します。


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a>ホスティングプロバイダーとしてクラウドボイスメールを構成する 

次のパラメーターを使用して、新しい-CsHostingProvider コマンドレットを使用して、クラウドボイスメールをホスティングプロバイダーとしてフロントエンドサーバーに構成します。

- **Identity**は、作成するホスティングプロバイダーの一意の文字列値識別子を指定します。たとえば、クラウドボイスメールです。 

- **Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。 このパラメーターは True に設定する必要があります。

- **EnabledSharedAddressSpace** は、ホスティング プロバイダーが共有 SIP アドレス スペース シナリオで使用されるかどうかを示します。 このパラメーターは True に設定する必要があります。

- **Hostソケット Susers**は、ホスティングプロバイダーが Skype For business Server アカウントをホストするために使用されるかどうかを示します。 このパラメーターは False に設定する必要があります。

- **Proxyfqdn**は、ホスティングプロバイダーによって使用されるプロキシサーバーの完全修飾ドメイン名 (FQDN) を指定します。たとえば、proxyserver.contoso.com のようになります。 この情報については、ホスティング プロバイダーに問い合わせてください。 この値は変更できません。 ホスティングプロバイダーがプロキシサーバーを変更した場合は、そのプロバイダーのエントリを削除してから再作成する必要があります。

- **Islocal**は、ホスティングプロバイダーによって使用されるプロキシサーバーが Skype For business server のトポロジ内に含まれているかどうかを示します。 このパラメーターは False に設定する必要があります。

たとえば、Skype for Business 管理シェルでは、次のコマンドレットにより、クラウドボイスメールがホスティングプロバイダーとして構成されます。


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>ホスト型ボイスメールポリシーを構成する

組織のボイスメールがクラウドボイスメールサービスにルーティングされるようにするには、組織に対してホスト型ボイスメールポリシーを構成する必要があります。 多くの場合、ホストボイスメールポリシーは1つだけ必要であり、グローバルポリシーを変更してすべてのニーズを満たすことができます。 組織で複数のホスト型ボイスメールポリシーが必要な場合は、set-cshostedvoicemailpolicy コマンドレットを使用してポリシーを追加できます。

グローバルポリシーを変更するには、組織と TenantID を更新した後、Skype for Business Server 管理シェルで次のコマンドを実行します。

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- **Destination**には、ホストされているクラウドボイスメールサービスの完全修飾ドメイン名 (FQDN) を指定します。 この値は、 **exap.um.outlook.com**に設定する必要があります。

- **組織**は、テナントに割り当てられている既定のドメインです。 この情報を取得するには、テナント管理者が office.com にログインし、[管理センター] アプリをクリックして、左側の [**セットアップ**] に移動し、[**ドメイン**] をクリックします。 例: mytenant.onmicrosoft.com。

    組織名は、Microsoft 365 または Office 365 の既定のドメイン名でもあります。

ホスト型ボイスメールポリシーが正常に作成されたことを確認するには、次のコマンドを実行します。

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>ホスト型ボイスメールポリシーの割り当て

既定では、グローバルにホストされるボイスメールポリシーがすべてのユーザーに割り当てられます。 別のポリシーを使用する場合は、ホストされたボイスメールにユーザーを有効にする前に、 [set-cshostedvoicemailpolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps)コマンドレットを使用して、必要なホストボイスメールポリシーをユーザーに付与する必要があります。

たとえば、次のコマンドを実行すると、非グローバルなホスト型ボイスメールポリシーがユーザーに割り当てられます。


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -PolicyName "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>クラウドボイスメールでユーザーを有効にする

ユーザーのボイスメールをクラウドボイスメールにルーティングできるようにするには、HostedVoiceMail パラメーターを指定して、ユーザーのボイス[メールコマンドレット](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)を使用します。 

たとえば、次のコマンドを実行すると、クラウドボイスメールのユーザーアカウントが有効になります。 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

このコマンドレットは、クラウドボイスメールポリシーがグローバル、サイト、またはユーザーレベルであることを確認します。--このユーザーに適用されます。 適用されるポリシーがない場合には、このコマンドレットは失敗します。  

次の例では、クラウドボイスメールのユーザーアカウントを無効にします。

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

このコマンドレットは、ホストされているボイスメールポリシーがないことを確認します。これは、グローバル、サイト、またはユーザーレベルで、このユーザーに適用されます。 適用されるポリシーがある場合には、このコマンドレットは失敗します。

> [!NOTE]
>  ユーザーは、Microsoft クラウドボイスメールサービスを使用するために、エンタープライズ voip が有効になっている必要があります。
