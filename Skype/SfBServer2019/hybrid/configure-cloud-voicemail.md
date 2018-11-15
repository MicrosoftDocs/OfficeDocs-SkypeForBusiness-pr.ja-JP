---
title: クラウド ボイスメール サービスを構成します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 5/9/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: ビジネス サーバーの Skype ホーム ユーザーのクラウド ベースのボイスメールが実装する方法について。
ms.openlocfilehash: 05c486ed338e8e77ab68f12a64c3a59646a157d0
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531913"
---
# <a name="configure-cloud-voicemail-service"></a>クラウド ボイスメール サービスを構成します。

## <a name="overview"></a>概要 
この資料では、オンプレミス ユーザーのビジネスを Skype のマイクロソフトのクラウドのボイスメール サービスを構成する方法について説明します。  

この資料では、ビジネスのサーバーでサポートされているトポロジでは、展開の Skype が既にあることと、ハイブリッドの接続を設定するための前提条件が満たされていると仮定します。

利点の詳細については、計画の考慮事項、およびクラウドのボイスメールを実装するための要件[計画クラウド ボイスメール サービス](plan-cloud-voicemail.md)を参照してください。




クラウドのボイス メールを構成するには、次のタスクが含まれます。

1.  [計画クラウドのボイスメール サービス](plan-cloud-voicemail.md)の説明に従って、前提条件を満たしていることを確認します。

2.  [ハイブリッド接続の計画](plan-hybrid-connectivity.md)と[構成のハイブリッドの接続](configure-hybrid-connectivity.md)で説明したように、ハイブリッド接続の設定を確認します。 

3.  [クラウド ボイスメールをエッジ サーバー上でホスティング プロバイダーとして構成する](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server)と、この資料に記載します。

4.  [ホスト ボイスメール ポリシーを構成する](#configure-a-hosted-voicemail-policy)この資料で説明されているようです。

5.  この資料で説明するよう[ホスト ボイスメール ポリシーを設定](#assign-a-hosted-voicemail-policy)。

6.  [クラウド ボイスメールに対してユーザーを有効にする](#enable-a-user-for-cloud-voicemail)この資料で説明されているようです。


## <a name="configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server"></a>エッジ サーバー上でホスティング プロバイダーとしてのクラウドのボイス メールの構成します。 

クラウドのボイスメールをエッジ サーバー上でホスティング プロバイダーとして構成するには、次のパラメーターを使用して新規 CsHostingProvider コマンドレットを使用しています。

- **Id**作成するホスティング プロバイダーの一意の文字列値の識別子を指定します。などのクラウドのボイスメールです。 

- **Enabled ** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。 このパラメーターを True に設定する必要があります。

- **EnabledSharedAddressSpace**では、ホスティング プロバイダーが共有 SIP アドレス スペースのシナリオで使用するかどうかを示します。 このパラメーターを True に設定する必要があります。

- **HostsOCSUsers**は、ビジネス サーバー アカウントの Skype をホストするホスティング プロバイダーを使用するかどうかを示します。 このパラメーターを False に設定する必要があります。

- **ProxyFQDN**は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。たとえば、proxyserver.contoso.com です。 この情報は、ホスティング プロバイダーに問い合わせてください。 この値を変更することはできません。 ホスティング プロバイダーは、そのプロキシ サーバーを変更する場合は、削除し、そのプロバイダーのエントリを再作成する必要があります。

- **IsLocal**は、ビジネスのサーバー トポロジの場合、Skype 内でホスティング プロバイダーで使用するプロキシ サーバーが含まれているかどうかを示します。 このパラメーターを False に設定する必要があります。

たとえば、ビジネス管理シェルの Skype で次のコマンドレットでは、クラウドのボイスメールとして構成ホスティング プロバイダー。


```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>ホスト ボイスメール ポリシーを構成します。

ボイスメールのクラウド サービスにルーティング組織のボイスメールを確認するのには、組織のホスト ボイスメール ポリシーを構成する必要があります。 多くの場合、1 つだけのホスト ボイスメール ポリシーが必要なと、すべてのニーズに対応するグローバル ポリシーを変更することができます。 組織は、複数のホスト ボイスメール ポリシーを必要とする場合は、cshostedvoicemailpolicy で新しいコマンドレットを使用してポリシーを追加できます。

グローバル ポリシーを変更するには、次コマンドを実行、Skype のビジネス サーバーの管理シェル、組織と TenantID を更新した後。

```
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -TenantID “11111111-1111-1111-1111-111111111111”
```

- **送信先**は、ホストされたクラウドのボイスメール サービスの完全修飾ドメイン名 (FQDN) を指定します。 **Exap.um.outlook.com**には、この値を設定する必要があります。

- **組織**では、テナントに割り当てられている既定のドメインです。 テナント管理者 office.com にログイン管理センターのアプリケーションに、左側の [**セットアップ**へ移動を [**ドメイン**] をクリックすることにより、この情報を取得できます。 例: mytenant.onmicrosoft.com。

    組織の名前が Office 365 の既定のドメイン名もあります。

- **TenantID**を使用して、Office 365 で、テナントを識別します。 詳細については[、Office 365 のテナント ID を検索](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b)」を参照してください。

ホスト ボイスメール ポリシーが正常に作成されたことを確認するには、次のコマンドを実行します。

```
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>ホスト ボイスメール ポリシーを割り当てる

既定でホストされているグローバル ボイスメール ポリシーがすべてのユーザーに割り当てられます。 ホスト ボイスメールに対してユーザーを有効にする前に、別のポリシーを使用する場合する必要があります最初ユーザーに与える目的のホスト ボイスメール ポリシー[許可 CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps)コマンドレットを使用しています。

たとえば、次のコマンドは、ユーザーに非グローバルのホスト ボイスメール ポリシーを割り当てます。


```
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>クラウド ボイスメールに対してユーザーを有効にします。

クラウドのボイスメールにルーティングするユーザーのボイス メールの呼び出しを有効にするには、HostedVoiceMail パラメーターを使用して[セット CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)コマンドレットを使用します。 

たとえば、次のコマンドでは、クラウドのボイスメールのユーザー アカウントを有効にします。 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

コマンドレットを確認するクラウドのボイスメール ポリシー--グローバル、サイト、またはユーザー レベル--は、このユーザーに適用されます。 ポリシーが適用されない場合、コマンドレットは失敗します。  

次の例では、クラウドのボイスメールのユーザー アカウントを無効にします。

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

コマンドレットを確認、グローバル--ホスト ボイスメール ポリシーがサイト、またはユーザー レベル--は、このユーザーに適用されません。 ポリシーが適用される場合は、コマンドレットが失敗します。

> [!NOTE]
>  ユーザーには、エンタープライズ ボイスのマイクロソフトのクラウドのボイスメール サービスを使用するのには有効になっている必要があります。