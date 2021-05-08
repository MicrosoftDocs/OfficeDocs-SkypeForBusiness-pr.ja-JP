---
title: Skype for Business Online ユーザーのフェデレーション サポートの構成
ms.reviewer: ''
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: '組織にSkype for Business展開する場合は、1 つ以上のオンラインユーザーのドメインSkype for Businessできます。 '
ms.openlocfilehash: c8e0481a85ff371e5454856d5b84a4dbccf50a97
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240531"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>オンラインユーザーのフェデレーション サポートSkype for Business構成するSkype for Business Server

次のいずれかの方法で、組織のユーザーに通信サービスを提供できます。

- 組織Skype for Business Server (オンプレミス サービスと呼 *ばれる)* に展開し、組織内Skype for Businessユーザー アカウントを設定します。
- ホスティング プロバイダーで Microsoft Skype for Business Online カスタマー アカウントをセットアップし、ホスティング プロバイダー (オンライン サービスと呼ばれる) を使用してユーザー アカウント *を設定します*。

組織にSkype for Business展開する場合は、1 つ以上のオンラインユーザーのドメインSkype for Businessできます。 オンプレミス Skype for Business 展開のユーザーと Skype for Business Online 顧客のユーザー間のフェデレーションを有効にするには、ドメインと Skype for Business Online のお客様のユーザーのサポートを構成する必要があります。

[!INCLUDE [sfbo-retirement-skype](../../../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]  
> このドキュメントでは、オンラインのお客様とのフェデレーションをサポートするために組織を構成する手順Skype for Business説明します。 このドキュメントでは、フェデレーションをサポートするためにオンライン顧客Skype for Business手順については説明されていません。

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>オンライン顧客とのフェデレーションSkype for Business前提条件

オンラインのお客様とフェデレーションSkype for Business、組織のユーザーの初期展開と構成Skype for Business Server完了している必要があります。 エクスポートできるものには、次のようなものがあります。

- 少なくとも 1 つのStandard Editionまたは 1 Enterprise Editionフロント エンド プールを組織に展開します。
- ユーザーの内部ユーザー アカウントを有効Skype for Business Server。
- 外部ユーザー アクセスをサポートするために必要な少なくとも 1 つのエッジ サーバーと他のコンポーネントを展開します。 詳細については、「フェデレーションと[外部アクセスの管理」を参照Skype for Business Server。](../managing-federation-and-external-access.md)
- 組織内のフェデレーション サポートを有効にし、フェデレーション ドメインによるアクセスを制御するための適切な方法を構成します。 詳細については、「リモート ユーザー [アクセスを有効または無効](../access-edge/enable-or-disable-remote-user-access.md) にする」および「組織の SIP フェデレーション プロバイダーを管理する [」を参照してください](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。
- 組織内のユーザーに対して外部ユーザー アクセスを有効にする。 詳細については、「外部ユーザー アクセス[ポリシーを有効なユーザーに割り当Skype for Businessする」を参照してください](../external-access-policies/assign-an-external-user-access-policy.md)。

## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>オンライン ドメインのフェデレーション サポートSkype for Business構成する

オンラインのお客様Skype for Businessフェデレーションするには、次の手順を実行する必要があります。

- オンライン 2010 のお客様 (Skype for Businessなど) のドメインのサポートを構成 contoso.onmicrosoft.com。 「オンラインユーザーとフェデレーションするための前提条件」で[Skype for Business、](#prerequisites-for-federating-with-a-skype-for-business-online-customer)組織のフェデレーションを既に有効にしている必要があります。 フェデレーションを有効にするには、フェデレーション ドメインによってアクセス制御に使用されるメソッドを指定する必要があります。 検出を使用するように組織を構成した場合は、組織の許可リストへのドメインの追加は省略できます。 ドメインの検出を有効にしなかった場合は、オンラインユーザーのドメイン名を許可Skype for Businessに追加する必要があります。 ドメイン名を追加するには、コントロール パネルSkype for Business Server **New-CSAllowedDomain コマンドレットを実行** します。 ドメインの検出を有効にするSkype for Business Serverコントロール パネルの使用の詳細については、「Manage SIP [federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md)for your organization in Skype for Business Server」 を参照してください。 **New-CSAllowedDomain** コマンドレットを使用してドメインを追加する方法の詳細については [、「New-CsAllowedDomain」を参照してください](/powershell/module/skype/New-CsAllowedDomain)。

  > [!NOTE]  
  > オンラインSkype for Businessは、複数のドメインを持つ場合があります。 複数のドメインとフェデレーションする場合は、フェデレーションをサポートする個々のドメインごとにサポートを構成する必要があります。また、Skype for Business Online のお客様の管理者は、フェデレーションする各ドメインのフェデレーションを有効にする必要があります。

- フェデレーションするオンライン顧客ドメインSkype for Businessホスティング プロバイダーのサポートを構成します。 ホスティング プロバイダーのサポートを構成するには、このセクションの手順に従います。

  > [!NOTE]  
  > この手順は、Skype for Business Online のお客様のドメインを持つフェデレーションにのみ必要です。フェデレーション パートナーの場所にオンプレミスで展開されているドメインとのフェデレーションには必要ありません。

### <a name="to-configure-support-for-a-hosting-provider"></a>ホスティング プロバイダーのサポートを構成するには

1. フロント エンド サーバーから、Skype for Business Server管理シェルを起動します。[スタート] をクリックし、[すべてのプログラム] をクリックし、[Skype for Business Server] をクリックし、[管理シェルSkype for Business Server **クリックします**。

2. **New-CsHostingProvider** コマンドレットを実行して、ホスティング プロバイダーを作成および構成します。たとえば、以下を実行します。

    ```powershell
    New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    ```

    上記の例では、次のパラメーターを設定しています。

    - **Identity** は、作成するホスティング プロバイダーの、一意の文字列値 からなる識別子を指定します。既存のプロバイダーがその ID で既に構成されている場合、このコマンドの実行は失敗します。

    - **ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。この値は変更できません。ホスティング プロバイダーがプロキシ サーバーを変更すると、そのプロバイダーのエントリを削除して再作成する必要があります。

    - **VerificationLevel** は、メッセージがホスティング プロバイダーから送信されたことを確認するために、そのプロバイダーから送信されたメッセージの検証方法 (または検証の有無) を指定します。

    - **Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効かどうかを示します。この値を **True** に設定しないと、2 つの組織間でメッセージを交換できません。

    - **EnabledSharedAddressSpace** では、共有 SIP アドレス スペース (分割ドメイン) シナリオで、ホスティング プロバイダーが使用されているかどうかを指定します。

    - **HostsOCSUsers は**、ホスティング プロバイダーを使用してアカウントをホストSkype for Business Serverします。 **False** は、プロバイダーが Microsoft Exchange アカウントなど、別の種類のアカウントをホストしていることを示します。

    - **IsLocal は**、ホスティング プロバイダーによって使用されるプロキシ サーバーが、ホスト トポロジ内に含まれているSkype for Business Serverします。

    このコマンドレットの使用の詳細については [、「New-CsHostingProvider」を参照してください](/powershell/module/skype/New-CsHostingProvider)。

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>オンラインユーザーとのフェデレーション用にユーザー アクセスSkype for Business構成する

組織内のすべてのユーザーがフェデレーション パートナーと通信できるようにするには、それらのユーザー アカウントを構成する必要があります。 この構成は、フェデレーションをサポートする Microsoft Skype for Businessオンライン顧客ドメインを含む、すべてのフェデレーション パートナーに適用されます。 ユーザー アカウントのフェデレーション サポートの構成の詳細については、「Configure policys to control [federationed](../external-access-policies/configure-policies-to-control-federated-user-access.md) user access and Assign an external user access policy to a Skype for Business 有効なユーザー」[を参照してください](../external-access-policies/assign-an-external-user-access-policy.md)。

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>オンラインのお客様とのSkype for Businessを確認Skype for Business Server

組織内のSkype for Businessユーザーがオンライン顧客のユーザーと通信Skype for Businessするには、次の手順を完了している必要があります。

- すべての前提条件を満たします。 このための作業には、内部サーバーとエッジ サーバーを展開する、組織に対してフェデレーションのサポートを有効にする、ユーザー アカウントを設定するなどがあります。 詳細については、「オンライン顧客[とフェデレーションするための前提条件Skype for Businessを参照してください](#prerequisites-for-federating-with-a-skype-for-business-online-customer)。
- 内部展開にドメイン アクセスのサポートを構成します。 これには、ホスト プロバイダー エントリの作成と、オンライン顧客のドメインからのアクセスを許可Skype for Business展開の構成が含まれます。 詳細については、「Configure federation support for a Skype for Business [Online ドメイン」を参照してください](#configure-federation-support-for-a-skype-for-business-online-domain)。
- フェデレーションをサポートするようにユーザー アカウントを構成します。 詳細については、「Configure user access for federation with a Skype for Business Online カスタマー [」を参照してください](#configure-user-access-for-federation-with-a-skype-for-business-online-customer)。

これらすべての手順を完了し、Skype for Business Online のお客様の管理者が、組織とのフェデレーションをサポートするためのオンライン サービスのすべての構成を完了したら、組織内の内部ユーザーと Skype for Business Online のお客様のユーザーとの間の通信をテストして通信を確認します。 通信が成功しない場合は、エッジ サーバーのログ ツールを使用してログ ファイルとトレース ファイルをキャプチャし、問題のトラブルシューティングを行います。
