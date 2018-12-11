---
title: オンライン ビジネスのお客様は Skype のフェデレーション サポートを構成します。
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '組織のビジネス用の Skype を導入する場合を統合 Skype の 1 つまたは複数のドメインを持つビジネス オンラインのお客様です。 '
ms.openlocfilehash: 978da18a4ae639e52dedd6971c1a2291c94cb9f1
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223368"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>ビジネス サーバーの Skype でのオンライン ビジネスのお客様は Skype のフェデレーション サポートを構成します。 

組織内のユーザーに通信サービスを提供するには次の方法のいずれかで。

  - ビジネス サーバーは、組織 (*設置型のサービス*と呼ばれます) と、組織内のビジネス ユーザーのアカウントの Skype の設定で Skype を配置しています。
  - (*オンライン サービス*と呼ばれます) をホストしているプロバイダーと、プロバイダーをホストしているユーザー アカウントを設定するとオンライン ビジネスの顧客アカウントの Microsoft Skype を設定します。

組織のビジネス用の Skype を導入する場合を統合 Skype の 1 つまたは複数のドメインを持つビジネス オンラインのお客様です。 ビジネス展開するため、設置型の Skype のユーザーとオンライン ビジネスのお客様は、Skype のユーザーの間でフェデレーションを有効にするには、ドメインおよびオンライン ビジネスのお客様の Skype のユーザーのサポートを行う必要があります。

> [!NOTE]  
> このドキュメントは、オンライン ビジネスのお客様は、Skype とのフェデレーションをサポートするために組織を構成する手順のみを説明します。 このドキュメントについては説明しません、フェデレーションをサポートするためにオンライン ビジネスのお客様の Skype を設定する手順です。 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Skype のオンライン ビジネスの顧客とのフェデレーションの前提条件

オンライン ビジネスのお客様は、Skype でフェデレーションをする必要がありますが完了している初期の展開と構成 Skype ビジネス サーバーの組織にします。 これには、次のポリシーが含まれます。

  - 少なくとも 1 つの Standard Edition サーバーまたは組織内の 1 つのエンタープライズ エディションのフロント エンド プールを展開します。 
  - ビジネス サーバーの Skype の内部のユーザー アカウントを有効にします。 
  - 外部ユーザー アクセスをサポートするために必要な 1 つ以上のエッジ サーバーと他のコンポーネントを展開します。 詳細については、[管理するフェデレーションと Skype のビジネス サーバーへの外部アクセス](../managing-federation-and-external-access.md)を参照してください。
  - 組織内でフェデレーション サポートを有効にして、フェデレーション ドメインによるアクセスを制御するための適切な方法を構成します。 詳細については、[組織のプロバイダーをフェデレーションする SIP を管理](../sip-providers/manage-sip-federated-providers-for-your-organization.md)し、[有効にするかリモート ユーザー アクセスを無効にする](../access-edge/enable-or-disable-remote-user-access.md)を参照してください。
  - ユーザーが組織内の外部ユーザー アクセスを有効にします。 詳細は[、Skype のビジネスの有効なユーザーへの外部ユーザー アクセス ポリシーを割り当てる](../external-access-policies/assign-an-external-user-access-policy.md)」を参照してください。



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Skype のビジネスのオンラインのドメインのフェデレーション サポートを構成します。

Skype のオンライン ビジネスの顧客とのフェデレーションには、次の手順を完了する必要があります。

  - ビジネス オンライン 2010 顧客 (contoso.onmicrosoft.com など) の Skype のドメインのサポートを構成します。 指定されている[ため、Skype のオンライン ビジネスの顧客とのフェデレーションの前提条件](#prerequisites-for-federating-with-a-skype-for-business-online-customer)、する必要があります既にフェデレーションを有効に組織にします。 フェデレーションを有効にするには、フェデレーション ドメインによってアクセスを制御する使用する方法を指定する必要があります。 探索を使用する組織を構成した場合、組織の許可リストにドメインを追加するはオプションです。 ドメインの検出を有効にしなかった場合は、許可されるドメインの一覧に、Skype のオンライン ビジネスのお客様のドメイン名を追加する必要があります。 ビジネス サーバーのコントロール パネルの Skype を使用するか、**新規 CSAllowedDomain**コマンドレットを実行して、ドメイン名を追加できます。 ビジネス サーバー コントロール パネルの [ドメインの探索を有効にするなどの Skype の使用の詳細については、「[組織は、ビジネスのサーバー用の Skype でプロバイダーをフェデレーションする SIP を管理](../sip-providers/manage-sip-federated-providers-for-your-organization.md)」を参照してください。 **新規 CSAllowedDomain**コマンドレットを使用してドメインを追加する詳細については、[新規 CsAllowedDomain](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAllowedDomain)を参照してください。

    > [!NOTE]  
    > オンライン ビジネスのお客様は、Skype では、複数のドメインを持つことができます。 複数のドメインとフェデレーションを行う場合は、個々 のドメインをフェデレーションをサポートしてそれぞれごとにドメインのフェデレーションを有効にする必要があります。 オンライン ビジネスのお客様の Skype の管理者のサポートを構成する必要があります。フェデレーションします。

  - オンライン ビジネスのお客様ドメインをフェデレーションする Skype のホスティング プロバイダーのサポートを構成します。 ホスティング プロバイダーのサポートを構成するのには、このセクションで、手順を使用します。

    > [!NOTE]  
    > この手順は、導入設置、フェデレーション パートナーの場所には、任意のドメインとのフェデレーションではなく、オンライン ビジネスのお客様に対する、Skype のドメインとのフェデレーションにのみ必要です。


### <a name="to-configure-support-for-a-hosting-provider"></a>ホスティング プロバイダーのサポートを構成するのには

1.  サーバーをフロント エンド サーバー、ビジネス サーバー管理シェルには、Skype を起動します。 [**スタート**] ボタン、[**すべてのプログラム**] をクリック、 **Skype ビジネス サーバーは**、をクリック**ビジネス サーバー管理シェルの Skype**です。

2.  作成し、ホスティング プロバイダーを構成する**新規 CsHostingProvider**コマンドレットを実行します。 たとえば、以下を実行します。
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    上述の例では、次のパラメーターが設定されます。
    
      - **Id**は、作成するホスティング プロバイダーの一意の文字列値の識別子を指定します。 既存のプロバイダーは、その Id を使用して既に構成されている場合、コマンドが失敗することを注意してください。
    
      - **ProxyFQDN**は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。 この値を変更することはできません。 ホスティング プロバイダーは、プロキシ サーバーを変更した場合は、削除し、そのプロバイダーのエントリを再作成する必要があります。
    
      - **VerificationLevel**を指定する方法 (または) ホスティング プロバイダーから送信されたメッセージがそのプロバイダーから送信されたことを確認することを確認します。
    
      - **Enabled ** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。この値を **True ** に設定しないと、2 つの組織間でメッセージを交換することはできません。
    
      - **EnabledSharedAddressSpace ** では、共有 SIP アドレス スペース (分割ドメイン) シナリオで、ホスティング プロバイダーが使用されているかどうかを指定します。
    
      - **HostsOCSUsers**は、ビジネス サーバー アカウントの Skype をホストするホスティング プロバイダーを使用するかどうかを示します。 **False ** は、プロバイダーが Microsoft Exchange アカウントなど、別の種類のアカウントをホストしていることを示します。
    
      - **IsLocal**は、ビジネスのサーバー トポロジの場合、Skype 内でホスティング プロバイダーで使用するプロキシ サーバーが含まれているかどうかを示します。
    
    このコマンドレットの使用方法の詳細は、[新規 CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider)を参照してください。

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>オンライン ビジネスのお客様は、Skype でのフェデレーション ユーザー アクセスを構成します。 

ユーザーを構成する必要があるために、組織内のすべてのユーザーのアカウントは、フェデレーション パートナーと通信するために許可します。 この構成は、フェデレーションをサポートしているオンライン ビジネスの顧客のドメインの任意の Microsoft Skype を含む、すべてのフェデレーション パートナーに対して適用されます。 ユーザー アカウントのフェデレーション サポートを構成する方法の詳細は、[制御するポリシーを構成するユーザーのアクセスを統合して](../external-access-policies/configure-policies-to-control-federated-user-access.md) [、Skype のビジネスの有効なユーザーへの外部ユーザー アクセス ポリシーを割り当てる](../external-access-policies/assign-an-external-user-access-policy.md)を参照してください。

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>ビジネス サーバーの Skype でのオンライン ビジネスのお客様は、Skype での通信を確認します。

オンライン ビジネスのお客様は、Skype のユーザーと通信するために、組織内のビジネス ユーザーで Skype を有効にするのには、次の手順を完了しましたする必要があります。

  - すべての前提条件が満たされています。 内部の配置が含まれ、エッジ サーバーでフェデレーションを有効にするが、組織、およびユーザー アカウントの設定をサポートします。 詳細については、[オンライン ビジネスのお客様は、Skype とのフェデレーションの前提条件](#prerequisites-for-federating-with-a-skype-for-business-online-customer)を参照してください。
  - 内部展開にドメイン アクセスのサポートを構成します。 これには、ホスト プロバイダーのエントリを作成して、Skype のオンライン ビジネスのお客様のドメインからのアクセスを許可するのには、配置の構成が含まれます。 詳細については、[構成のフェデレーションを Skype ビジネス オンラインのドメインのためのサポート](#configure-federation-support-for-a-skype-for-business-online-domain)を参照してください。
  - フェデレーションをサポートするためにユーザー アカウントを構成します。 詳細については、[オンライン ビジネスのお客様は、Skype とのフェデレーションを構成するユーザーのアクセス](#configure-user-access-for-federation-with-a-skype-for-business-online-customer)を参照してください。

すべてを実行する手順と、Skype の管理者のオンライン ビジネスのお客様は、組織とのフェデレーションをサポートするためにオンライン サービスのすべての構成を完了するため後の間の通信をテストすることによって通信することを確認します。オンライン ビジネスのお客様の Skype のユーザー、組織内の内部ユーザーです。 通信が失敗した場合、問題を解決するためにログ ファイルとトレース ファイルをキャプチャするのには、エッジ サーバーからのログ収集ツールを使用します。 