---
title: Skype for Business Online ユーザーのフェデレーション サポートの構成
ms.reviewer: ''
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: '組織内にSkype for Businessを展開する場合は、1 つ以上のSkype for Business Online 顧客のドメインとフェデレーションできます。 '
ms.openlocfilehash: d180de014c0a7479eb5dc7a6fb60e00e5b136f24
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676229"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Skype for Business ServerでSkype for Business Online のお客様のフェデレーション サポートを構成する

次のいずれかの方法で、組織のユーザーに通信サービスを提供できます。

- 組織内にSkype for Business Serverを展開し (*オンプレミス サービス* と呼ばれます)、組織内のSkype for Businessユーザー アカウントを設定します。
- ホスティング プロバイダーを使用して Microsoft Skype for Business Online カスタマー アカウントを設定し、ホスティング プロバイダー (オンライン サービス と呼ばれる) でユーザー アカウント *を* 設定します。

組織内にSkype for Businessを展開する場合は、1 つ以上のSkype for Business Online 顧客のドメインとフェデレーションできます。 オンプレミスのSkype for Business展開のユーザーとSkype for Business Online 顧客のユーザー間のフェデレーションを有効にするには、Skype for Business Online 顧客のドメインとユーザーのサポートを構成する必要があります。

[!INCLUDE [sfbo-retirement-skype](../../../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]  
> このドキュメントでは、Skype for Business Online のお客様とのフェデレーションをサポートするように組織を構成する手順について説明します。 このドキュメントでは、フェデレーションをサポートするようにSkype for Business Online のお客様を構成する手順については説明しません。

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Skype for Business Online のお客様とのフェデレーションの前提条件

Skype for Business Online のお客様とフェデレーションするには、組織内のSkype for Business Serverの初期デプロイと構成が既に完了している必要があります。 エクスポートできるものには、次のようなものがあります。

- 組織内の少なくとも 1 つのStandard Edition サーバーまたは 1 つのEnterprise Editionフロントエンド プールをデプロイする。
- Skype for Business Serverの内部ユーザー アカウントを有効にする。
- 少なくとも 1 つのエッジ サーバーと、外部ユーザー アクセスをサポートするために必要なその他のコンポーネントをデプロイします。 詳細については、「[Skype for Business Serverへのフェデレーションと外部アクセスの管理」を](../managing-federation-and-external-access.md)参照してください。
- 組織内でフェデレーション サポートを有効にし、フェデレーション ドメインによるアクセスを制御するための適切な方法を構成します。 詳細については、「 [リモート ユーザー アクセスを有効または無効にする](../access-edge/enable-or-disable-remote-user-access.md) 」と「 [組織の SIP フェデレーション プロバイダーの管理」を参照してください](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。
- 組織内のユーザーに対して外部ユーザー アクセスを有効にする。 詳細については、「[Skype for Businessが有効なユーザーに外部ユーザー アクセス ポリシーを割り当てる](../external-access-policies/assign-an-external-user-access-policy.md)」を参照してください。

## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Skype for Business Online ドメインのフェデレーション サポートを構成する

Skype for Business Online のお客様とのフェデレーションでは、次の手順を完了する必要があります。

- Skype for Business Online 2010 のお客様 (contoso.onmicrosoft.com など) のドメインのサポートを構成します。 [Skype for Business Online 顧客とのフェデレーションの前提条件](#prerequisites-for-federating-with-a-skype-for-business-online-customer)で指定されているように、組織のフェデレーションを既に有効にしている必要があります。 フェデレーションを有効にするには、フェデレーション ドメインによってアクセス制御に使用されるメソッドを指定する必要があります。 検出を使用するように組織を構成した場合は、組織の許可リストへのドメインの追加は省略できます。 ドメイン検出を有効にしなかった場合は、Skype for Business Online のお客様のドメイン名を許可されたドメインの一覧に追加する必要があります。 ドメイン名は、Skype for Business Server コントロール パネルを使用するか、**New-CSAllowedDomain** コマンドレットを実行して追加できます。 ドメインの検出の有効化など、Skype for Business Server コントロール パネルの使用の詳細については、「[Skype for Business Serverで組織の SIP フェデレーション プロバイダーを管理する](../sip-providers/manage-sip-federated-providers-for-your-organization.md)」を参照してください。 **New-CSAllowedDomain** コマンドレットを使用してドメインを追加する方法の詳細については、「[New-CsAllowedDomain」を](/powershell/module/skype/New-CsAllowedDomain)参照してください。

  > [!NOTE]  
  > Skype for Business Online のお客様は、複数のドメインを持つことができます。 複数のドメインとフェデレーションする場合は、フェデレーションをサポートする個々のドメインごとにサポートを構成する必要があります。また、Skype for Business Online のお客様の管理者は、各ドメインのフェデレーションを有効にする必要があります。

- フェデレーションするSkype for Business Online 顧客ドメインのホスティング プロバイダーのサポートを構成します。 ホスティング プロバイダーのサポートを構成するには、このセクションの手順に従います。

  > [!NOTE]  
  > この手順は、フェデレーション パートナーの場所にオンプレミスで展開されているドメインとのフェデレーションではなく、Skype for Business Online のお客様のドメインとのフェデレーションにのみ必要です。

### <a name="to-configure-support-for-a-hosting-provider"></a>ホスティング プロバイダーのサポートを構成するには

1. フロント エンド サーバーから、Skype for Business Server管理シェルを起動します。 [**スタート]** をクリックし、[**すべてのプログラム**] をクリック **し、[Skype for Business Server**] をクリックして、[**管理シェルSkype for Business Server**] をクリックします。

2. **New-CsHostingProvider** コマンドレットを実行して、ホスティング プロバイダーを作成および構成します。 たとえば、以下を実行します。

    ```powershell
    New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    ```

    上記の例では、次のパラメーターを設定しています。

    - **Identity** は、作成するホスティング プロバイダーの、一意の文字列値 からなる識別子を指定します。既存のプロバイダーがその ID で既に構成されている場合、このコマンドの実行は失敗します。

    - **ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。この値は変更できません。ホスティング プロバイダーがプロキシ サーバーを変更すると、そのプロバイダーのエントリを削除して再作成する必要があります。

    - **VerificationLevel** は、メッセージがホスティング プロバイダーから送信されたことを確認するために、そのプロバイダーから送信されたメッセージの検証方法 (または検証の有無) を指定します。

    - **Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効かどうかを示します。この値を **True** に設定しないと、2 つの組織間でメッセージを交換できません。

    - **EnabledSharedAddressSpace** では、共有 SIP アドレス スペース (分割ドメイン) シナリオで、ホスティング プロバイダーが使用されているかどうかを指定します。

    - **HostsOCSUsers は、** ホスティング プロバイダーを使用してSkype for Business Serverアカウントをホストするかどうかを示します。 **False** は、プロバイダーが Microsoft Exchange アカウントなど、別の種類のアカウントをホストしていることを示します。

    - **IsLocal は**、ホスティング プロバイダーによって使用されるプロキシ サーバーがSkype for Business Server トポロジ内に含まれているかどうかを示します。

    このコマンドレットの使用の詳細については、「 [New-CsHostingProvider」を](/powershell/module/skype/New-CsHostingProvider)参照してください。

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Skype for Business Online のお客様とのフェデレーションのユーザー アクセスを構成する

組織内のすべてのユーザーがフェデレーション パートナーと通信できるようにするには、それらのユーザー アカウントを構成する必要があります。 この構成は、フェデレーションをサポートするすべての Microsoft Skype for Business Online 顧客ドメインを含むすべてのフェデレーション パートナーに適用されます。 ユーザー アカウントのフェデレーション サポートの構成の詳細については、「[フェデレーション ユーザー アクセスを制御するポリシーを構成する](../external-access-policies/configure-policies-to-control-federated-user-access.md)」および「[Skype for Businessが有効なユーザーに外部ユーザー アクセス ポリシーを割り当てる](../external-access-policies/assign-an-external-user-access-policy.md)」を参照してください。

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Skype for Business ServerでSkype for Business Online のお客様との通信を確認する

組織内のSkype for BusinessユーザーがSkype for Business Online 顧客のユーザーと通信できるようにするには、次の手順を完了している必要があります。

- すべての前提条件を満たします。 このための作業には、内部サーバーとエッジ サーバーを展開する、組織に対してフェデレーションのサポートを有効にする、ユーザー アカウントを設定するなどがあります。 詳細については、「[Skype for Business Online のお客様とのフェデレーションの前提条件」](#prerequisites-for-federating-with-a-skype-for-business-online-customer)を参照してください。
- 内部展開にドメイン アクセスのサポートを構成します。 これには、ホスト プロバイダー エントリの作成と、Skype for Business Online 顧客のドメインからのアクセスを許可するようにデプロイを構成することが含まれます。 詳細については、「[Skype for Business Online ドメインのフェデレーション サポートを構成する」を](#configure-federation-support-for-a-skype-for-business-online-domain)参照してください。
- フェデレーションをサポートするようにユーザー アカウントを構成します。 詳細については、「[Skype for Business Online のお客様とのフェデレーションのユーザー アクセスを構成する](#configure-user-access-for-federation-with-a-skype-for-business-online-customer)」を参照してください。

これらのすべての手順を完了し、Skype for Business Online のお客様の管理者が、組織とのフェデレーションをサポートするためのオンライン サービスのすべての構成を完了したら、組織内の内部ユーザーとSkype for Business Online 顧客のユーザー間の通信をテストして通信を確認します。 通信が成功しない場合は、エッジ サーバーのログ ツールを使用してログ ファイルとトレース ファイルをキャプチャし、問題のトラブルシューティングを行います。
