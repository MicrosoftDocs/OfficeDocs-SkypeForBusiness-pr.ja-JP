---
title: Skype for Business Online ユーザーのフェデレーション サポートの構成
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
localization_priority: Normal
description: '組織に Skype for Business を展開すると、1つ以上の Skype for Business Online のユーザーのドメインとフェデレーションを行うことができます。 '
ms.openlocfilehash: c6cf36abbbf8876a8aa349d4576b45220517b89e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280111"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Skype for business Server の Skype for Business Online ユーザーに対するフェデレーションサポートの構成 

次のいずれかの方法で、組織内のユーザーに通信サービスを提供できます。

  - 組織に Skype for Business Server (*オンプレミスサービス*とも呼ばれます) を展開して、組織内の Skype for business ユーザーアカウントをセットアップします。
  - ホスティングプロバイダーを使用して Microsoft Skype for Business Online の顧客アカウントを設定し、ホスティングプロバイダー (*オンラインサービス*とも呼ばれます) を使用してユーザーアカウントを設定します。

組織に Skype for Business を展開すると、1つ以上の Skype for Business Online のユーザーのドメインとフェデレーションを行うことができます。 オンプレミスの Skype for Business 展開と Skype for Business Online ユーザーのユーザーの間のフェデレーションを有効にするには、Skype for Business Online ユーザーのドメインとユーザーのサポートを構成する必要があります。

> [!NOTE]  
> このドキュメントでは、Skype for Business Online のお客様とのフェデレーションをサポートするように組織を構成する手順についてのみ説明します。 このドキュメントでは、Skype for Business Online のお客様がフェデレーションをサポートするように構成する手順について説明していません。 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Skype for Business Online のお客様とのフェデレーションの前提条件

Skype for Business Online のユーザーとフェデレーションを行うには、組織内の Skype for Business Server の最初の展開と構成を既に完了している必要があります。 これには、次のポリシーが含まれます。

  - 少なくとも1つの Standard Edition サーバーまたは1つの Enterprise Edition フロントエンドプールを組織に展開します。 
  - Skype for Business Server の内部ユーザーアカウントを有効にします。 
  - 少なくとも1つのエッジサーバーと、外部ユーザーのアクセスをサポートするために必要なその他のコンポーネントを展開します。 詳細については、「 [Skype For Business Server へのフェデレーションと外部アクセスの管理](../managing-federation-and-external-access.md)」を参照してください。
  - 組織内でフェデレーションサポートを有効にし、フェデレーションドメインによるアクセスを制御するための適切なメソッドを構成します。 詳細については、「[リモートユーザーアクセスを有効または無効](../access-edge/enable-or-disable-remote-user-access.md)にする」および「[組織の SIP フェデレーションプロバイダーを管理](../sip-providers/manage-sip-federated-providers-for-your-organization.md)する」を参照してください。
  - 組織内のユーザーに対して外部ユーザーアクセスを有効にします。 詳細については、「 [Skype For business が有効なユーザーに外部ユーザーアクセスポリシーを割り当てる](../external-access-policies/assign-an-external-user-access-policy.md)」を参照してください。



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Skype for Business Online ドメインのフェデレーションサポートを構成する

Skype for Business Online のお客様とのフェデレーションを行うには、次の手順を実行する必要があります。

  - Skype for Business Online 2010 ユーザーのドメインのサポートを構成します (たとえば、contoso.onmicrosoft.com)。 [Skype For Business Online のお客様とのフェデレーションの前提条件](#prerequisites-for-federating-with-a-skype-for-business-online-customer)として、組織のフェデレーションを既に有効にしている必要があります。 フェデレーションを有効にするには、フェデレーションドメインによるアクセスを制御するために使用するメソッドを指定する必要があります。 検出機能を使用するように組織を構成している場合、ドメインを組織の許可リストに追加するオプションは省略できます。 ドメインの検出を有効にしなかった場合は、Skype for Business Online のユーザーのドメイン名を、許可されているドメイン一覧に追加する必要があります。 ドメイン名を追加するには、Skype for Business Server コントロールパネルを使用するか、または、**新しい-CSAllowedDomain**コマンドレットを実行します。 Skype for Business Server コントロールパネルの使い方 (ドメインの検出を有効にするなど) について詳しくは、「 [skype For Business Server で組織の SIP フェデレーションプロバイダーを管理](../sip-providers/manage-sip-federated-providers-for-your-organization.md)する」をご覧ください。 **新しい-csalloweddomain**コマンドレットを使用してドメインを追加する方法の詳細については、「[新しい-csalloweddomain](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAllowedDomain)」を参照してください。

    > [!NOTE]  
    > Skype for Business Online のお客様は、複数のドメインを持つことができます。 複数のドメインとフェデレーションを行う場合は、フェデレーションをサポートする個々のドメインに対してサポートを構成する必要があります。また、Skype for Business Online の管理者は、それぞれのドメインについてフェデレーションを有効にする必要があります。フェデレーションされます。

  - フェデレーションを行う Skype for Business Online 顧客ドメインのホスティングプロバイダーのサポートを構成します。 このセクションの手順を使用して、ホスティングプロバイダーのサポートを構成します。

    > [!NOTE]  
    > この手順は、Skype for Business Online のユーザーのドメインとフェデレーションを行う場合にのみ必要です。フェデレーションパートナーの場所にオンプレミスで展開されているドメインとのフェデレーションには使用できません。


### <a name="to-configure-support-for-a-hosting-provider"></a>ホスティングプロバイダーのサポートを構成するには

1.  フロントエンドサーバーから、Skype for Business Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**] をクリックします。次に、[skype for business server] をクリックし、[ **Skype for business server 管理シェル**] をクリックします。 ****

2.  **新しい-CsHostingProvider**コマンドレットを実行して、ホスティングプロバイダーを作成し、構成します。 たとえば、以下を実行します。
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    上述の例では、次のパラメーターが設定されます。
    
      - **Id**は、作成するホスティングプロバイダーの一意の文字列値識別子を指定します。 既存のプロバイダーが既にその Id で構成されている場合、コマンドは失敗します。
    
      - **ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。 この値は変更できません。 ホスティングプロバイダーによってプロキシサーバーが変更された場合は、削除して、そのプロバイダーのエントリを再作成する必要があります。
    
      - **VerificationLevel**は、ホスティングプロバイダーから送信されたメッセージを、そのプロバイダーから送信されたものであるかどうかを確認するために、どのようにするかを指定します。
    
      - **Enabled ** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。この値を **True ** に設定しないと、2 つの組織間でメッセージを交換することはできません。
    
      - **EnabledSharedAddressSpace ** では、共有 SIP アドレス スペース (分割ドメイン) シナリオで、ホスティング プロバイダーが使用されているかどうかを指定します。
    
      - **Hostているユーザー**は、ホスティングプロバイダーが Skype For business Server アカウントをホストするために使用されているかどうかを示します。 **False ** は、プロバイダーが Microsoft Exchange アカウントなど、別の種類のアカウントをホストしていることを示します。
    
      - **Islocal**は、ホスティングプロバイダーによって使用されたプロキシサーバーが Skype For business server トポロジ内に含まれているかどうかを示します。
    
    このコマンドレットの使い方の詳細については、「[新しい-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider)」を参照してください。

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Skype for Business Online ユーザーとのフェデレーション用にユーザーアクセスを構成する 

フェデレーションパートナーとの通信を許可するには、組織内のすべてのユーザーのユーザーアカウントを構成する必要があります。 この構成は、フェデレーションをサポートしている Microsoft Skype for Business Online の顧客ドメインなど、すべてのフェデレーションパートナーに適用されます。 ユーザーアカウントのフェデレーションサポートの構成の詳細については、「フェデレーションされた[ユーザーアクセスを制御するためのポリシーの構成](../external-access-policies/configure-policies-to-control-federated-user-access.md)」および「 [Skype for business 対応ユーザーへの外部ユーザーアクセスポリシーの割り当て](../external-access-policies/assign-an-external-user-access-policy.md)」を参照してください。

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Skype for business Server の Skype for Business Online ユーザーとの通信を確認する

組織内の Skype for Business ユーザーが Skype for Business Online 顧客のユーザーと通信できるようにするには、次の手順を完了しておく必要があります。

  - すべての前提条件を満たしていること。 これには、内部サーバーとエッジサーバーの展開、組織に対するフェデレーションサポートの有効化、ユーザーアカウントのセットアップなどが含まれます。 詳細については、「 [Skype For Business Online ユーザーとのフェデレーションの前提条件](#prerequisites-for-federating-with-a-skype-for-business-online-customer)」を参照してください。
  - 内部展開でドメインアクセスのサポートが構成されている。 これには、ホストプロバイダーエントリの作成、および Skype for Business Online の顧客のドメインからのアクセスを許可するように展開を構成することが含まれます。 詳細については、「 [Skype For Business Online ドメインのフェデレーションサポートを構成する](#configure-federation-support-for-a-skype-for-business-online-domain)」を参照してください。
  - フェデレーションをサポートするようにユーザーアカウントを構成しました。 詳細については、「 [Skype For Business Online ユーザーとのフェデレーション用にユーザーアクセスを構成する](#configure-user-access-for-federation-with-a-skype-for-business-online-customer)」を参照してください。

すべての手順を完了して、Skype for Business Online の管理者が組織とのフェデレーションをサポートするために、オンラインサービスのすべての設定を完了したら、組織内の内部ユーザーと、Skype for Business Online のユーザーのユーザー。 通信が失敗した場合は、エッジサーバーのログツールを使用して、ログファイルとトレースファイルをキャプチャし、問題のトラブルシューティングを行います。 
