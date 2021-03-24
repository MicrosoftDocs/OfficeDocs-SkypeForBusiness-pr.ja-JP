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
description: '組織に Skype for Business を展開する場合は、1 つ以上の Skype for Business Online のお客様のドメインとフェデレーションできます。 '
ms.openlocfilehash: c241af4700662c11366a71a55afad28ed3f8b7db
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098953"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Skype for Business Server での Skype for Business Online 顧客のフェデレーション サポートの構成 

次のいずれかの方法で、組織のユーザーに通信サービスを提供できます。

  - 組織内に Skype for Business Server を展開し (オンプレミス サービスと呼 *ばれる)、* 組織内で Skype for Business ユーザー アカウントを設定します。
  - ホスティング プロバイダーを使用して Microsoft Skype for Business Online カスタマー アカウントをセットアップし、ホスティング プロバイダー (オンライン サービスと呼ばれる) を使用してユーザー アカウント *を設定します*。

組織に Skype for Business を展開する場合は、1 つ以上の Skype for Business Online のお客様のドメインとフェデレーションできます。 オンプレミスの Skype for Business 展開のユーザーと Skype for Business Online のお客様のユーザー間のフェデレーションを有効にするには、Skype for Business Online のお客様のドメインとユーザーのサポートを構成する必要があります。

> [!NOTE]  
> このドキュメントでは、Skype for Business Online のお客様とのフェデレーションをサポートするために組織を構成する手順のみを説明します。 このドキュメントでは、フェデレーションをサポートするために Skype for Business Online のお客様を構成する手順については説明されていません。 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Skype for Business Online のお客様とのフェデレーションの前提条件

Skype for Business Online のお客様とフェデレーションするには、組織の Skype for Business Server の初期展開と構成が既に完了している必要があります。 エクスポートできるものには、次のようなものがあります。

  - 組織に少なくとも 1 つの Standard Edition サーバーまたは 1 つの Enterprise Edition フロントエンド プールを展開します。 
  - Skype for Business Server の内部ユーザー アカウントを有効にします。 
  - 外部ユーザー アクセスをサポートするために必要な少なくとも 1 つのエッジ サーバーと他のコンポーネントを展開します。 詳細については [、「Skype for Business Server へのフェデレーションと外部アクセスの管理」を参照してください](../managing-federation-and-external-access.md)。
  - 組織内のフェデレーション サポートを有効にし、フェデレーション ドメインによるアクセスを制御するための適切な方法を構成します。 詳細については、「リモート ユーザー [アクセスを有効または無効](../access-edge/enable-or-disable-remote-user-access.md) にする」および「組織の SIP フェデレーション プロバイダーを管理する [」を参照してください](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。
  - 組織内のユーザーに対して外部ユーザー アクセスを有効にする。 詳細については、「外部ユーザー アクセス ポリシーを Skype for Business が有効なユーザーに [割り当てる」を参照してください](../external-access-policies/assign-an-external-user-access-policy.md)。



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Skype for Business Online ドメインのフェデレーション サポートを構成する

Skype for Business Online のお客様とのフェデレーションでは、次の手順を実行する必要があります。

  - Skype for Business Online 2010 のお客様のドメインのサポートを構成します (たとえば、contoso.onmicrosoft.com)。 「Skype [for Business Online のお客様](#prerequisites-for-federating-with-a-skype-for-business-online-customer)とのフェデレーションの前提条件」で指定されている通り、組織のフェデレーションを既に有効にしている必要があります。 フェデレーションを有効にするには、フェデレーション ドメインによってアクセス制御に使用されるメソッドを指定する必要があります。 検出を使用するように組織を構成した場合は、組織の許可リストへのドメインの追加は省略できます。 ドメインの検出を有効にしなかった場合は、Skype for Business Online のお客様のドメイン名を許可されたドメイン の一覧に追加する必要があります。 ドメイン名は、Skype for Business Server コントロール パネルを使用するか **、New-CSAllowedDomain コマンドレットを実行して追加** できます。 ドメインの検出を有効にするなどの Skype for Business Server コントロール パネルの使用の詳細については [、「Skype for Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md)で組織の SIP フェデレーション プロバイダーを管理する」を参照してください。 **New-CSAllowedDomain** コマンドレットを使用してドメインを追加する方法の詳細については [、「New-CsAllowedDomain」を参照してください](/powershell/module/skype/New-CsAllowedDomain)。

    > [!NOTE]  
    > Skype for Business Online のお客様は、複数のドメインを持つ場合があります。 複数のドメインとフェデレーションする場合は、フェデレーションをサポートする個々のドメインごとにサポートを構成する必要があります。また、Skype for Business Online のお客様の管理者は、フェデレーションする各ドメインのフェデレーションを有効にする必要があります。

  - フェデレーションする Skype for Business Online カスタマー ドメインのホスティング プロバイダーのサポートを構成します。 ホスティング プロバイダーのサポートを構成するには、このセクションの手順に従います。

    > [!NOTE]  
    > この手順は、Skype for Business Online のお客様のドメインを持つフェデレーションにのみ必要です。フェデレーション パートナーの場所にオンプレミスで展開されているドメインとのフェデレーションには必要ありません。


### <a name="to-configure-support-for-a-hosting-provider"></a>ホスティング プロバイダーのサポートを構成するには

1.  フロント エンド サーバーから、Skype for Business Server 管理シェルを起動する: [スタート] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business Server]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。

2.  **New-CsHostingProvider** コマンドレットを実行して、ホスティング プロバイダーを作成および構成します。 たとえば、以下を実行します。
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    上記の例では、次のパラメーターを設定しています。
    
      - **Identity** は、作成するホスティング プロバイダーの、一意の文字列値 からなる識別子を指定します。既存のプロバイダーがその ID で既に構成されている場合、このコマンドの実行は失敗します。
    
      - **ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。この値は変更できません。ホスティング プロバイダーがプロキシ サーバーを変更すると、そのプロバイダーのエントリを削除して再作成する必要があります。
    
      - **VerificationLevel** は、メッセージがホスティング プロバイダーから送信されたことを確認するために、そのプロバイダーから送信されたメッセージの検証方法 (または検証の有無) を指定します。
    
      - **Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効かどうかを示します。この値を **True** に設定しないと、2 つの組織間でメッセージを交換できません。
    
      - **EnabledSharedAddressSpace** では、共有 SIP アドレス スペース (分割ドメイン) シナリオで、ホスティング プロバイダーが使用されているかどうかを指定します。
    
      - **HostsOCSUsers は** 、ホスティング プロバイダーを使用して Skype for Business Server アカウントをホストするかどうかを示します。 **False** は、プロバイダーが Microsoft Exchange アカウントなど、別の種類のアカウントをホストしていることを示します。
    
      - **IsLocal は** 、ホスティング プロバイダーによって使用されるプロキシ サーバーが Skype for Business Server トポロジ内に含まれているかどうかを示します。
    
    このコマンドレットの使用の詳細については [、「New-CsHostingProvider」を参照してください](/powershell/module/skype/New-CsHostingProvider)。

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Skype for Business Online のお客様とのフェデレーション用にユーザー アクセスを構成する 

組織内のすべてのユーザーがフェデレーション パートナーと通信できるようにするには、それらのユーザー アカウントを構成する必要があります。 この構成は、フェデレーションをサポートする Microsoft Skype for Business Online カスタマー ドメインを含む、すべてのフェデレーション パートナーに適用されます。 ユーザー アカウントのフェデレーション サポートの構成の詳細については、「Configure policys to control [federationed](../external-access-policies/configure-policies-to-control-federated-user-access.md) user access and Assign an external user access policy [to a Skype for Business enabled user」を参照してください](../external-access-policies/assign-an-external-user-access-policy.md)。

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Skype for Business Server で Skype for Business Online のお客様との通信を確認する

組織内の Skype for Business ユーザーが Skype for Business Online のお客様のユーザーと通信するには、次の手順を完了している必要があります。

  - すべての前提条件を満たします。 このための作業には、内部サーバーとエッジ サーバーを展開する、組織に対してフェデレーションのサポートを有効にする、ユーザー アカウントを設定するなどがあります。 詳細については、「Skype for Business Online のお客様との [フェデレーションの前提条件」を参照してください](#prerequisites-for-federating-with-a-skype-for-business-online-customer)。
  - 内部展開にドメイン アクセスのサポートを構成します。 これには、ホスト プロバイダー エントリの作成と、Skype for Business Online のお客様のドメインからのアクセスを許可する展開の構成が含まれます。 詳細については [、「Configure federation support for a Skype for Business Online ドメイン」を参照してください](#configure-federation-support-for-a-skype-for-business-online-domain)。
  - フェデレーションをサポートするようにユーザー アカウントを構成します。 詳細については [、「Configure user access for federation with a Skype for Business Online customer」を参照してください](#configure-user-access-for-federation-with-a-skype-for-business-online-customer)。

これらすべての手順を完了し、Skype for Business Online のお客様の管理者が、組織とのフェデレーションをサポートするためのオンライン サービスのすべての構成を完了したら、組織内の内部ユーザーと Skype for Business Online のお客様のユーザーとの間の通信をテストして通信を確認します。 通信が成功しない場合は、エッジ サーバーのログ ツールを使用してログ ファイルとトレース ファイルをキャプチャし、問題のトラブルシューティングを行います。