---
title: オンプレミス ユーザー向けクラウド ボイスメール サービスの構成
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
description: Skype for Business Server に保存されているユーザーのクラウドベースのボイスメールを実装する手順。
ms.openlocfilehash: a9c308189a5dc70c85382f638f30f52c0ac69bdb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118986"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a>オンプレミス ユーザー向けクラウド ボイスメール サービスの構成

## <a name="overview"></a>概要 
この記事では、Skype for Business オンプレミス ユーザー用に Microsoft Cloud ボイスメール サービスを構成する方法について説明します。  

この記事では、サポートされているトポロジに Skype for Business Server が既に展開済みであり、ハイブリッド接続をセットアップするための前提条件を満たしていることを前提とします。

クラウド ボイスメールを実装するための利点、計画上の考慮事項、および要件の詳細については、「Plan Cloud ボイスメール サービス」 [を参照してください](plan-cloud-voicemail.md)。




クラウド ボイスメールの構成には、次のタスクが含まれます。

1.  「Plan Cloud ボイスメール サービス」の説明に従って、 [前提条件を満たしていることを確認します](plan-cloud-voicemail.md)。

2.  「ハイブリッド接続の計画」および「ハイブリッド接続の構成[](plan-hybrid-connectivity.md)」の説明に従って、ハイブリッド接続をセットアップ[してください。](configure-hybrid-connectivity.md) 

3.  [この記事で説明するように、](#configure-cloud-voicemail-as-the-hosting-provider) フロントエンド サーバー上のホスティング プロバイダーとしてクラウド ボイスメールを構成します。

4.  [この記事の説明に従って、](#configure-a-hosted-voicemail-policy) ホストされたボイスメール ポリシーを構成します。

5.  [この記事の説明に従って、](#assign-a-hosted-voicemail-policy) ホストされたボイスメール ポリシーを割り当てる。

6.  [この記事の説明に従って、クラウド](#enable-a-user-for-cloud-voicemail) ボイスメールのユーザーを有効にしてください。


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a>クラウド ボイスメールをホスティング プロバイダーとして構成する 

次のパラメーターを使用して、クラウド ボイスメールをフロントエンド サーバーのホスティング プロバイダーNew-CsHostingProvider構成します。

- **Identity** は、作成するホスティング プロバイダーの一意の文字列値識別子を指定します。たとえば、クラウド ボイスメール。 

- **Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。 このパラメーターは True に設定する必要があります。

- **EnabledSharedAddressSpace** は、ホスティング プロバイダーが共有 SIP アドレス スペース シナリオで使用されるかどうかを示します。 このパラメーターは True に設定する必要があります。

- **HostsOCSUsers は** 、ホスティング プロバイダーを使用して Skype for Business Server アカウントをホストするかどうかを示します。 このパラメーターは False に設定する必要があります。

- **ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。たとえば、proxyserver.contoso.com。 この情報については、ホスティング プロバイダーに問い合わせてください。 この値は変更できません。 ホスティング プロバイダーがプロキシ サーバーを変更する場合は、そのプロバイダーのエントリを削除してから再作成する必要があります。

- **IsLocal は** 、ホスティング プロバイダーによって使用されるプロキシ サーバーが Skype for Business Server トポロジ内に含まれているかどうかを示します。 このパラメーターは False に設定する必要があります。

たとえば、Skype for Business 管理シェルで、次のコマンドレットはクラウド ボイスメールをホスティング プロバイダーとして構成します。


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>ホストされたボイスメール ポリシーを構成する

組織のボイスメールがクラウド ボイスメール サービスにルーティングされるのを確認するには、組織のホストボイスメール ポリシーを構成する必要があります。 多くの場合、ホストされるボイスメール ポリシーは 1 つのみ必要であり、すべてのニーズに合わせてグローバル ポリシーを変更できます。 組織で複数のホストされたボイスメール ポリシーが必要な場合は、new-cshostedvoicemailpolicy コマンドレットを使用してポリシーを追加できます。

グローバル ポリシーを変更するには、組織と TenantID を更新した後、Skype for Business Server 管理シェルで次のコマンドを実行します。

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- **Destination** は、ホストされたクラウド ボイスメール サービスの完全修飾ドメイン名 (FQDN) を指定します。 この値は、次の値に **exap.um.outlook.com。**

- **組織** は、テナントに割り当てられている既定のドメインです。 この情報を取得するには、テナント管理者が office.com にログインし、管理センター アプリをクリックし、左側の[セットアップ] に移動し、[ドメイン] を **クリックします**。 たとえば、次の mytenant.onmicrosoft.com。

    組織名は、Microsoft 365 または 365 の既定Officeです。

ホストされたボイスメール ポリシーが正常に作成されたことを確認するには、次のコマンドを実行します。

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>ホストされたボイスメール ポリシーの割り当て

既定では、グローバル ホストボイスメール ポリシーは、すべてのユーザーに割り当てられます。 別のポリシーを使用する場合は、ホストされたボイスメールのユーザーを有効にする前に、 [まず Grant-CSHostedVoicemailPolicy](/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) コマンドレットを使用して、ユーザーに必要なホスト型ボイスメール ポリシーを付与する必要があります。

たとえば、次のコマンドは、グローバル以外のホストボイスメール ポリシーをユーザーに割り当てします。


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -PolicyName "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>クラウド ボイスメールのユーザーを有効にする

ユーザーのボイスメール通話をクラウド ボイスメールにルーティングするには [、HostedVoiceMail パラメーターで Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) コマンドレットを使用します。 

たとえば、次のコマンドを使用すると、クラウド ボイスメールのユーザー アカウントが有効になります。 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

このコマンドレットは、グローバル、サイト、またはユーザー レベルのクラウド ボイスメール ポリシーが、このユーザーに適用されるのを確認します。 適用されるポリシーがない場合には、このコマンドレットは失敗します。  

次の例では、クラウド ボイスメールのユーザー アカウントを無効にします。

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

このコマンドレットは、ホストされたボイスメール ポリシー (グローバル、サイト、またはユーザー レベル) がこのユーザーに適用されていないか確認します。 適用されるポリシーがある場合には、このコマンドレットは失敗します。

> [!NOTE]
>  Microsoft Cloud ボイスメール サービスを使用するには、ユーザーがエンタープライズ音声を有効にする必要があります。