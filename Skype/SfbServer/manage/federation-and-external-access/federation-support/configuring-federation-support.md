---
title: Skype for Business Online のお客様のためのフェデレーションサポートの構成
ms.reviewer: ''
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: '組織で Skype for Business を展開する場合、1つまたは複数の Skype for Business Online のユーザーのドメインとフェデレーションを行うことができます。 '
ms.openlocfilehash: b7488d21463782a978c9a3d6263d9fdfc2e59dd9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037287"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Skype for business Server で Skype for Business Online のお客様のためのフェデレーションサポートを構成する 

次のいずれかの方法で、組織のユーザーに通信サービスを提供できます。

  - 組織内の Skype for Business Server (*オンプレミスサービス*とも呼ばれます) を展開し、組織で skype for business ユーザーアカウントをセットアップします。
  - ホスティングプロバイダーを使用して Microsoft Skype for Business Online の顧客アカウントを設定し、ホスティングプロバイダー (*オンラインサービス*とも呼ばれます) を使用してユーザーアカウントを設定します。

組織で Skype for Business を展開する場合、1つまたは複数の Skype for Business Online のユーザーのドメインとフェデレーションを行うことができます。 オンプレミスの Skype for Business 展開と Skype for Business Online のユーザーのユーザー間のフェデレーションを有効にするには、Skype for Business Online のお客様のドメインとユーザーのサポートを構成する必要があります。

> [!NOTE]  
> このドキュメントでは、Skype for Business Online のお客様とのフェデレーションをサポートするように組織を構成する手順についてのみ説明します。 このドキュメントでは、フェデレーションをサポートするように Skype for Business Online のお客様を構成する手順については説明しません。 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Skype for Business Online の顧客とのフェデレーションの前提条件

Skype for Business Online の顧客とのフェデレーションを行うには、組織内の Skype for Business Server の初期の展開と構成が既に完了している必要があります。 エクスポートできるものには、次のようなものがあります。

  - 少なくとも1つの Standard Edition サーバーまたは1つの Enterprise Edition フロントエンドプールを組織に展開します。 
  - Skype for Business Server の内部ユーザーアカウントを有効にします。 
  - 少なくとも1つのエッジサーバーと、外部ユーザーアクセスをサポートするために必要なその他のコンポーネントを展開します。 詳細については、「 [Skype For Business Server へのフェデレーションと外部アクセスの管理](../managing-federation-and-external-access.md)」を参照してください。
  - 組織内でフェデレーションのサポートを有効にし、フェデレーションドメインによるアクセスを制御するための適切な方法を構成します。 詳細については、「 [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md) 」および「 [Manage SIP フェデレーションプロバイダー for your organization](../sip-providers/manage-sip-federated-providers-for-your-organization.md)」を参照してください。
  - 組織内のユーザーの外部ユーザーアクセスを有効にします。 詳細については、「 [Skype For business が有効なユーザーへの外部ユーザーアクセスポリシーの割り当て](../external-access-policies/assign-an-external-user-access-policy.md)」を参照してください。



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Skype for Business Online ドメインのフェデレーションサポートを構成する

Skype for Business Online ユーザーとのフェデレーションでは、次の手順を完了する必要があります。

  - Skype for Business Online 2010 お客様のドメインのサポートを構成します (たとえば、contoso.onmicrosoft.com)。 [Skype For Business Online の顧客とのフェデレーションの前提条件](#prerequisites-for-federating-with-a-skype-for-business-online-customer)で指定されているように、組織のフェデレーションが既に有効になっている必要があります。 フェデレーションを有効にするには、フェデレーション ドメインによってアクセス制御に使用されるメソッドを指定する必要があります。 検出を使用するように組織を構成した場合は、組織の許可リストへのドメインの追加は省略できます。 ドメインの検出を有効にしなかった場合は、Skype for Business Online のユーザーのドメイン名を許可されたドメインの一覧に追加する必要があります。 ドメイン名を追加するには、Skype for Business Server コントロールパネルを使用するか、または**新しい-CSAllowedDomain**コマンドレットを実行します。 ドメインの検出を有効にするなど、Skype for Business Server コントロールパネルの使用の詳細については、「 [MANAGE SIP フェデレーションプロバイダー for Your skype For Business server](../sip-providers/manage-sip-federated-providers-for-your-organization.md)」を参照してください。 **新しい-csalloweddomain**コマンドレットを使用してドメインを追加する方法の詳細については、「 [New-csalloweddomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain)」を参照してください。

    > [!NOTE]  
    > Skype for Business Online のお客様は、複数のドメインを持つことができます。 複数のドメインとのフェデレーションを行う場合は、フェデレーションをサポートする個々のドメインのサポートを構成する必要があります。また、Skype for Business Online の管理者は、各ドメインのフェデレーションを有効にする必要があります。フェデレーションされます。

  - フェデレーションを行う Skype for Business Online の顧客ドメインのホスティングプロバイダーのサポートを構成します。 ホスティング プロバイダーのサポートを構成するには、このセクションの手順に従います。

    > [!NOTE]  
    > この手順は、Skype for Business Online のドメインとのフェデレーションの場合にのみ必要であり、フェデレーションパートナーの場所に社内で展開されているドメインとのフェデレーションには必要ありません。


### <a name="to-configure-support-for-a-hosting-provider"></a>ホスティング プロバイダーのサポートを構成するには

1.  フロントエンドサーバーから、Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for Business server**]、[ **skype for business server 管理シェル**] の順にクリックします。

2.  **New-CsHostingProvider** コマンドレットを実行して、ホスティング プロバイダーを作成および構成します。 たとえば、以下を実行します。
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    上記の例では、次のパラメーターを設定しています。
    
      - **Identity** は、作成するホスティング プロバイダーの、一意の文字列値 からなる識別子を指定します。既存のプロバイダーがその ID で既に構成されている場合、このコマンドの実行は失敗します。
    
      - **ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。この値は変更できません。ホスティング プロバイダーがプロキシ サーバーを変更すると、そのプロバイダーのエントリを削除して再作成する必要があります。
    
      - **VerificationLevel** は、メッセージがホスティング プロバイダーから送信されたことを確認するために、そのプロバイダーから送信されたメッセージの検証方法 (または検証の有無) を指定します。
    
      - **Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効かどうかを示します。この値を **True** に設定しないと、2 つの組織間でメッセージを交換できません。
    
      - **EnabledSharedAddressSpace** では、共有 SIP アドレス スペース (分割ドメイン) シナリオで、ホスティング プロバイダーが使用されているかどうかを指定します。
    
      - **Hostソケット Susers**は、ホスティングプロバイダーが Skype For business Server アカウントをホストするために使用されるかどうかを示します。 **False** は、プロバイダーが Microsoft Exchange アカウントなど、別の種類のアカウントをホストしていることを示します。
    
      - **Islocal**は、ホスティングプロバイダーによって使用されるプロキシサーバーが Skype For business server のトポロジ内に含まれているかどうかを示します。
    
    このコマンドレットの使用の詳細については、「 [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)」を参照してください。

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Skype for Business Online の顧客とのフェデレーションのユーザーアクセスを構成する 

組織内のすべてのユーザーがフェデレーション パートナーと通信できるようにするには、それらのユーザー アカウントを構成する必要があります。 この構成は、フェデレーションをサポートする Microsoft Skype for Business Online の顧客ドメインを含む、すべてのフェデレーションパートナーに適用されます。 ユーザーアカウントのフェデレーションサポートの構成の詳細については、「 [Configure policies to control フェデレーション user access](../external-access-policies/configure-policies-to-control-federated-user-access.md) 」および「 [Skype for business が有効なユーザーに対する外部ユーザーアクセスポリシーの割り当て](../external-access-policies/assign-an-external-user-access-policy.md)」を参照してください。

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Skype for business Server で Skype for Business Online の顧客との通信を確認する

組織内の Skype for Business ユーザーが Skype for business Online のユーザーと通信できるようにするには、次の手順を完了している必要があります。

  - すべての前提条件を満たします。 このための作業には、内部サーバーとエッジ サーバーを展開する、組織に対してフェデレーションのサポートを有効にする、ユーザー アカウントを設定するなどがあります。 詳細については、「 [Skype For Business Online のお客様とのフェデレーションの前提条件](#prerequisites-for-federating-with-a-skype-for-business-online-customer)」を参照してください。
  - 内部展開にドメイン アクセスのサポートを構成します。 これには、ホストプロバイダエントリの作成と、Skype for Business Online のお客様のドメインからのアクセスを許可するように展開を構成することが含まれます。 詳細については、「 [Skype For Business Online ドメインのフェデレーションサポートを構成](#configure-federation-support-for-a-skype-for-business-online-domain)する」を参照してください。
  - フェデレーションをサポートするようにユーザー アカウントを構成します。 詳細については、「 [Skype For Business Online 顧客とのフェデレーションのユーザーアクセスを構成する](#configure-user-access-for-federation-with-a-skype-for-business-online-customer)」を参照してください。

これらの手順をすべて完了した後、Skype for Business Online のお客様の管理者が、組織とのフェデレーションをサポートするためにオンラインサービスのすべての構成を完了したら、通信をテストすることにより、組織内の内部ユーザーと、Skype for Business Online のお客様のユーザー。 通信が成功しなかった場合は、エッジサーバーのログツールを使用して、問題のトラブルシューティングのためにログとトレースファイルをキャプチャします。 
