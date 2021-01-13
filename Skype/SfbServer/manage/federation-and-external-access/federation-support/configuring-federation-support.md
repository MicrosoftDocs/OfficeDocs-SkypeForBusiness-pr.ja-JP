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
description: '組織に Skype for Business を展開する場合は、1 つ以上の Skype for Business Online ユーザーのドメインとフェデレーションできます。 '
ms.openlocfilehash: f09e717af9e5209a0bb4bfdeb0ea50abbdaf7f86
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817237"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Skype for Business Server での Skype for Business Online 顧客のフェデレーション サポートの構成 

次のいずれかの方法で、組織のユーザーに通信サービスを提供できます。

  - 組織内での Skype for Business Server の展開 (オンプレミス サービスと呼 *ばれる)* と、組織内の Skype for Business ユーザー アカウントのセットアップ。
  - ホスティング プロバイダーを使用して Microsoft Skype for Business Online 顧客アカウントを設定し、ホスティング プロバイダー (オンライン サービスと呼ばれる) を使用してユーザー アカウント *を設定します*。

組織に Skype for Business を展開する場合は、1 つ以上の Skype for Business Online ユーザーのドメインとフェデレーションできます。 オンプレミスの Skype for Business 展開のユーザーと Skype for Business Online 顧客のユーザーとの間のフェデレーションを有効にするには、ドメインと Skype for Business Online 顧客のユーザーのサポートを構成する必要があります。

> [!NOTE]  
> このドキュメントでは、Skype for Business Online のお客様とのフェデレーションをサポートするために組織を構成する手順のみを説明します。 このドキュメントでは、フェデレーションをサポートするために Skype for Business Online のお客様を構成する手順については説明されていません。 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Skype for Business Online のお客様とのフェデレーションの前提条件

Skype for Business Online のお客様とフェデレーションを行う場合は、組織内の Skype for Business Server の初期展開と構成が既に完了している必要があります。 エクスポートできるものには、次のようなものがあります。

  - 組織内に少なくとも 1 つの Standard Edition サーバーまたは 1 つの Enterprise Edition フロントエンド プールを展開する。 
  - Skype for Business Server の内部ユーザー アカウントの有効化。 
  - 少なくとも 1 つのエッジ サーバーと、外部ユーザー アクセスをサポートするために必要な他のコンポーネントの展開。 詳細については [、「Skype for Business Server へのフェデレーションと外部アクセスの管理」を参照してください](../managing-federation-and-external-access.md)。
  - 組織内でフェデレーション サポートを有効にし、フェデレーション ドメインによるアクセスを制御するための適切な方法を構成する。 詳細については、「リモート ユーザー [アクセスを有効または無効にする」および](../access-edge/enable-or-disable-remote-user-access.md) 「組織の SIP フェデレーション [プロバイダーを管理する」を参照してください](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。
  - 組織内のユーザーに対する外部ユーザー アクセスの有効化。 詳細については [、「Skype for Business が有効なユーザーに外部ユーザー アクセス ポリシーを割り当てる」を参照してください](../external-access-policies/assign-an-external-user-access-policy.md)。



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Skype for Business Online ドメインのフェデレーション サポートを構成する

Skype for Business Online のお客様とのフェデレーションには、次の手順を完了する必要があります。

  - Skype for Business Online 2010 のお客様のドメインのサポートを構成します (contoso.onmicrosoft.com)。 [Skype for Business Online の](#prerequisites-for-federating-with-a-skype-for-business-online-customer)顧客とのフェデレーションの前提条件で指定されている通り、組織のフェデレーションは既に有効になっている必要があります。 フェデレーションを有効にするには、フェデレーション ドメインによってアクセス制御に使用されるメソッドを指定する必要があります。 検出を使用するように組織を構成した場合は、組織の許可リストへのドメインの追加は省略できます。 ドメインの検出を有効にしなかった場合は、Skype for Business Online 顧客のドメイン名を許可されたドメインの一覧に追加する必要があります。 ドメイン名は、Skype for Business Server コントロール パネルを使用するか **、New-CSAllowedDomain** コマンドレットを実行して追加できます。 ドメインの検出の有効化など、Skype for Business Server コントロール パネルの使用の詳細については [、「Skype for Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md)で組織の SIP フェデレーション プロバイダーを管理する」を参照してください。 **New-CSAllowedDomain** コマンドレットを使用してドメインを追加する方法の詳細については [、「New-CsAllowedDomain」を参照してください](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain)。

    > [!NOTE]  
    > Skype for Business Online のお客様は複数のドメインを持つ場合があります。 複数のドメインとフェデレーションを行う場合は、フェデレーションをサポートする個々のドメインごとにサポートを構成する必要があります。また、Skype for Business Online のお客様の管理者は、フェデレーションを行う各ドメインに対してフェデレーションを有効にする必要があります。

  - フェデレーションを行う Skype for Business Online 顧客ドメインのホスティング プロバイダーのサポートを構成します。 ホスティング プロバイダーのサポートを構成するには、このセクションの手順に従います。

    > [!NOTE]  
    > この手順は、Skype for Business Online ユーザーのドメインとのフェデレーションにのみ必要です。フェデレーション パートナーの場所にオンプレミスで展開されているドメインとのフェデレーションには必要ありません。


### <a name="to-configure-support-for-a-hosting-provider"></a>ホスティング プロバイダーのサポートを構成するには

1.  フロントエンド サーバーから、Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business Server]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。 

2.  **New-CsHostingProvider** コマンドレットを実行して、ホスティング プロバイダーを作成および構成します。 たとえば、以下を実行します。
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    上記の例では、次のパラメーターを設定しています。
    
      - **Identity** は、作成するホスティング プロバイダーの、一意の文字列値 からなる識別子を指定します。既存のプロバイダーがその ID で既に構成されている場合、このコマンドの実行は失敗します。
    
      - **ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。この値は変更できません。ホスティング プロバイダーがプロキシ サーバーを変更すると、そのプロバイダーのエントリを削除して再作成する必要があります。
    
      - **VerificationLevel** は、メッセージがホスティング プロバイダーから送信されたことを確認するために、そのプロバイダーから送信されたメッセージの検証方法 (または検証の有無) を指定します。
    
      - **Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効かどうかを示します。この値を **True** に設定しないと、2 つの組織間でメッセージを交換できません。
    
      - **EnabledSharedAddressSpace** では、共有 SIP アドレス スペース (分割ドメイン) シナリオで、ホスティング プロバイダーが使用されているかどうかを指定します。
    
      - **HostsOCSUsers は** 、ホスティング プロバイダーを使用して Skype for Business Server アカウントをホストするかどうかを示します。 **False** は、プロバイダーが Microsoft Exchange アカウントなど、別の種類のアカウントをホストしていることを示します。
    
      - **IsLocal** は、ホスティング プロバイダーが使用するプロキシ サーバーが Skype for Business Server トポロジ内に含まれているかどうかを示します。
    
    このコマンドレットの使用の詳細については [、「New-CsHostingProvider」を参照してください](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)。

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Skype for Business Online 顧客とのフェデレーション用にユーザー アクセスを構成する 

組織内のすべてのユーザーがフェデレーション パートナーと通信できるようにするには、それらのユーザー アカウントを構成する必要があります。 この構成は、フェデレーションをサポートする Microsoft Skype for Business Online の顧客ドメインを含む、すべてのフェデレーション パートナーに適用されます。 ユーザー アカウントのフェデレーション サポートの構成の詳細については、「Configure [policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md) and [Assign an external user access policy to a Skype for Business enabled user](../external-access-policies/assign-an-external-user-access-policy.md).

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Skype for Business Server で Skype for Business Online のお客様との通信を確認する

組織内の Skype for Business ユーザーが Skype for Business Online 顧客のユーザーと通信するには、次の手順を完了している必要があります。

  - すべての前提条件を満たします。 このための作業には、内部サーバーとエッジ サーバーを展開する、組織に対してフェデレーションのサポートを有効にする、ユーザー アカウントを設定するなどがあります。 詳細については、「Skype for Business Online 顧客とのフェデレーションの [前提条件」を参照してください](#prerequisites-for-federating-with-a-skype-for-business-online-customer)。
  - 内部展開にドメイン アクセスのサポートを構成します。 これには、ホスト プロバイダー エントリの作成と、Skype for Business Online の顧客のドメインからのアクセスを許可する展開の構成が含まれます。 詳細については [、「Skype for Business Online ドメインのフェデレーション サポートを構成する」を参照してください](#configure-federation-support-for-a-skype-for-business-online-domain)。
  - フェデレーションをサポートするようにユーザー アカウントを構成します。 詳細については、「Skype for Business Online 顧客とのフェデレーション用にユーザー [アクセスを構成する」を参照してください](#configure-user-access-for-federation-with-a-skype-for-business-online-customer)。

これらすべての手順を完了し、Skype for Business Online 顧客の管理者が組織とのフェデレーションをサポートするためにオンライン サービスのすべての構成を完了したら、組織内の内部ユーザーと Skype for Business Online ユーザーの間の通信をテストして通信を確認します。 通信に成功しない場合は、エッジ サーバーのログ ツールを使用してログ ファイルとトレース ファイルをキャプチャし、問題のトラブルシューティングを行います。 
