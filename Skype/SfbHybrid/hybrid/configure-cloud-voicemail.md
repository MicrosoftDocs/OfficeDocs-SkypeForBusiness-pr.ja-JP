---
title: オンプレミス ユーザークラウド ボイスメールサービスを構成する
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
description: クラウド ベースのボイスメールを実装する手順については、Skype for Business Server。
ms.openlocfilehash: 8a0c04d90d77b0843ef8b9097abec91c04ee7bb336bf04e0cbfcc9c7fe5fe38a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337257"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a>オンプレミス ユーザークラウド ボイスメールサービスを構成する

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


## <a name="overview"></a>概要 
この記事では、オンプレミスユーザーにMicrosoft クラウド ボイスメールサービスをSkype for Businessする方法について説明します。  

この記事では、既にサポートされているSkype for Business Server展開済みであり、ハイブリッド接続をセットアップするための前提条件を満たしていることを前提とします。

サービスを実装するための利点、計画の考慮事項、および要件の詳細については、「Plan[クラウド ボイスメール サービス」をクラウド ボイスメールしてください](plan-cloud-voicemail.md)。




構成にはクラウド ボイスメールタスクが含まれます。

1.  「サービスの計画」の説明に従って、前提条件[を満たしていることをクラウド ボイスメールします](plan-cloud-voicemail.md)。

2.  「ハイブリッド接続の計画」および「ハイブリッド接続の構成[](plan-hybrid-connectivity.md)」の説明に従って、ハイブリッド接続をセットアップ[してください。](configure-hybrid-connectivity.md) 

3.  [このクラウド ボイスメール説明するように](#configure-cloud-voicemail-as-the-hosting-provider)、フロントエンド サーバー上のホスティング プロバイダーとして構成します。

4.  [この記事の説明に従って、](#configure-a-hosted-voicemail-policy) ホストされたボイスメール ポリシーを構成します。

5.  [この記事の説明に従って、](#assign-a-hosted-voicemail-policy) ホストされたボイスメール ポリシーを割り当てる。

6.  [この記事の説明に従ってクラウド ボイスメール](#enable-a-user-for-cloud-voicemail)を有効にしてください。


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a>ホスティング クラウド ボイスメールとして構成する 

フロントエンド サーバークラウド ボイスメールホスティング プロバイダーとして構成するには、次のパラメーターを使用して New-CsHostingProviderコマンドレットを使用します。

- **Identity** は、作成するホスティング プロバイダーの一意の文字列値識別子を指定します。たとえば、クラウド ボイスメール。 

- **Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。 このパラメーターは True に設定する必要があります。

- **EnabledSharedAddressSpace** は、ホスティング プロバイダーが共有 SIP アドレス スペース シナリオで使用されるかどうかを示します。 このパラメーターは True に設定する必要があります。

- **HostsOCSUsers は**、ホスティング プロバイダーを使用してアカウントをホストSkype for Business Serverします。 このパラメーターは False に設定する必要があります。

- **ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。たとえば、proxyserver.contoso.com。 この情報については、ホスティング プロバイダーに問い合わせてください。 この値は変更できません。 ホスティング プロバイダーがプロキシ サーバーを変更する場合は、そのプロバイダーのエントリを削除してから再作成する必要があります。

- **IsLocal は**、ホスティング プロバイダーによって使用されるプロキシ サーバーが、ホスト トポロジ内に含まれているSkype for Business Serverします。 このパラメーターは False に設定する必要があります。

たとえば、次のコマンドレットSkype for Business管理シェルで、ホスト プロバイダーとしてクラウド ボイスメールを構成します。


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>ホストされたボイスメール ポリシーを構成する

組織のボイスメールが クラウド ボイスメール サービスにルーティングされるのを確認するには、組織のホスト型ボイスメール ポリシーを構成する必要があります。 多くの場合、ホストされるボイスメール ポリシーは 1 つのみ必要であり、すべてのニーズに合わせてグローバル ポリシーを変更できます。 組織で複数のホストされたボイスメール ポリシーが必要な場合は、new-cshostedvoicemailpolicy コマンドレットを使用してポリシーを追加できます。

グローバル ポリシーを変更するには、組織と TenantID を更新したSkype for Business Server管理シェルで次のコマンドを実行します。

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- **Destination** は、ホストされているドメイン サービスの完全修飾ドメイン名 (FQDN) をクラウド ボイスメールします。 この値は、次の値に **exap.um.outlook.com。**

- **組織** は、テナントに割り当てられている既定のドメインです。 この情報を取得するには、テナント管理者が office.com にログインし、管理センター アプリをクリックし、左側の[セットアップ] に移動し、[ドメイン] を **クリックします**。 たとえば、次の mytenant.onmicrosoft.com。

    組織名は、組織または組織の既定のドメインMicrosoft 365 Office 365。

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

## <a name="enable-a-user-for-cloud-voicemail"></a>ユーザーに対してユーザーを有効クラウド ボイスメール

ユーザーのボイスメール通話を クラウド ボイスメール にルーティングするには[、HostedVoiceMail パラメーターで Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps)コマンドレットを使用します。 

たとえば、次のコマンドを使用すると、ユーザー アカウントが有効クラウド ボイスメール。 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

このコマンドレットは、クラウド ボイスメール、サイト、またはユーザー レベルのポリシーがこのユーザーに適用されるのを確認します。 適用されるポリシーがない場合には、このコマンドレットは失敗します。  

次の例では、ユーザー アカウントを無効にクラウド ボイスメール。

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

このコマンドレットは、ホストされたボイスメール ポリシー (グローバル、サイト、またはユーザー レベル) がこのユーザーに適用されていないか確認します。 適用されるポリシーがある場合には、このコマンドレットは失敗します。

> [!NOTE]
>  ユーザーがエンタープライズ 音声サービスを使用するには、エンタープライズ音声Microsoft クラウド ボイスメール必要があります。