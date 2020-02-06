---
title: フェデレーションおよびパブリック IM 接続の有効化または無効化
ms.reviewer: ''
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
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
description: フェデレーションのサポートは、信頼された顧客またはパートナー組織のアカウントを持っているユーザー (パートナーのドメインや、サポートしているパブリックインスタントメッセージング (IM) プロバイダーのユーザーを含む) を有効にして、ユーザーとの共同作業を行うことができるようにする必要があります。組織.
ms.openlocfilehash: 2e24d670295a751c4cd3f41048fe1807b0fe1723
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818388"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a>Skype for Business Server でフェデレーションとパブリック IM 接続を有効または無効にする

フェデレーションのサポートは、信頼された顧客またはパートナー組織のアカウントを持っているユーザー (パートナーのドメインや、サポートしているパブリックインスタントメッセージング (IM) プロバイダーのユーザーを含む) を有効にして、ユーザーとの共同作業を行うことができるようにする必要があります。組織. また、ホストされている exchange サービスプロバイダーを使用して、メールボックスが Microsoft Exchange Online などのホスティングされた Exchange サービス上にあるエンタープライズボイスユーザーに、ボイスメールを提供する必要があります。 これらの外部ドメインとの信頼関係を確立したら、これらのドメインのユーザーに対して、展開にアクセスして、Skype for Business Server の通信に参加することを許可することができます。 この信頼関係はフェデレーションと呼ばれており、Active Directory の信頼関係に関連していない、または依存していません。

フェデレーションドメインのユーザーによるアクセスをサポートするには、フェデレーションを有効にする必要があります。 組織のフェデレーションを有効にする場合は、次のオプションを実装するかどうかも指定する必要があります。

  - **パートナードメインの検出**   を有効にするこのオプションを有効にした場合、Skype for business Server はドメインネームシステム (DNS) レコードを使用して、[許可したドメイン] 一覧にないドメインを検出し、検出されたフェデレーションパートナーから受信トラフィックを自動的に評価し、信頼レベル、トラフィック量、および管理者設定に基づいてそのトラフィックを制限 このオプションが選択されていない場合、フェデレーションされたユーザーのアクセス許可は、[許可したドメイン] リストに含めるドメイン内のユーザーに対してのみ有効になります。 このオプションが選択されているかどうかにかかわらず、フェデレーションドメインでアクセスエッジサービスを実行している特定のサーバーへのアクセスを制限するなど、個々のドメインをブロックまたは許可するように指定することができます。 フェデレーションドメインによるアクセスの制御の詳細については、「許可されている[外部ドメインのサポートを構成する](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)」を参照してください。

  - **フェデレーションパートナー**    にアーカイブの免責事項を送信する免責事項は、展開にアーカイブすることが適切に行われるフェデレーションパートナーに送信されます。 フェデレーションパートナードメインとの外部通信のアーカイブをサポートしている場合は、アーカイブの免責事項の通知を有効にして、メッセージがアーカイブされていることをパートナーに警告する必要があります。

後でフェデレーションドメインのユーザーによるアクセスを一時的または完全に禁止する場合は、組織のフェデレーションを無効にできます。 このセクションの手順を使用して、組織のフェデレーションされたユーザーアクセスを有効または無効にします。組織でサポートする必要のあるフェデレーションオプションを指定するなどの操作を行います。

> [!NOTE]  
> 組織でフェデレーションを有効にすると、アクセスエッジサービスを実行しているサーバーでフェデレーションドメインへのルーティングがサポートされるようになります。 フェデレーションドメイン内のユーザーは、フェデレーションされたユーザーアクセスをサポートするために少なくとも1つのポリシーを構成するまで、組織内の IM または会議に参加することはできません。 パブリック IM サービスプロバイダーのユーザーは、パブリック IM 接続をサポートするように少なくとも1つのポリシーを構成するまで、組織内の IM または会議に参加することはできません。 Skype for Business Server は、ホストされた音声を構成するまで、ホストされている Exchange サービス上にメールボックスが置かれているユーザーに対して、通話応答、Outlook Voice Access (ボイスメールを含む)、または自動応答サービスを提供することはできません。ルーティング情報を提供するメールポリシー。 他の組織のフェデレーションドメインのユーザーと通信するためのポリシーを構成する方法について詳しくは、「[組織の SIP フェデレーションドメインを管理](../sip-domains/manage-sip-federated-domains-for-your-organization.md)する」をご覧ください。 さらに、IM サービスプロバイダーのユーザーとの通信をサポートする必要がある場合は、それをサポートするようにポリシーを構成し、サポートする個々のサービスプロバイダーのサポートも構成する必要があります。 詳細については、「[組織の SIP フェデレーションプロバイダーを管理](../sip-providers/manage-sip-federated-providers-for-your-organization.md)する」を参照してください。


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>組織のフェデレーションされたユーザーアクセスを有効または無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**アクセスエッジ構成**] をクリックします。

4.  [**アクセスエッジの構成**] ページで [**グローバル**] をクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  [ **Access Edge 構成の編集**] で、次のいずれかの操作を行います。
    
      - 組織のフェデレーションされたユーザーアクセスを有効にするには、[**フェデレーションユーザーとの通信を有効**にする] チェックボックスをオンにします。
    
      - 組織のフェデレーションされたユーザーアクセスを無効にするには、[フェデレーションされ**たユーザーとの通信を有効**にする] チェックボックスをオフにします。

6.  [**フェデレーションユーザーとの通信を有効に**する] チェックボックスをオンにした場合は、次の操作を行います。
    
    1.  パートナードメインの自動検出をサポートするには、[**パートナードメイン探索を有効に**する] チェックボックスをオンにします。
    
    2.  組織で外部通信のアーカイブがサポートされている場合は、[**フェデレーションパートナーにアーカイブの免責事項を送信する**] チェックボックスをオンにします。

7.  [**コミット**] をクリックします。

フェデレーションユーザーが Skype for Business Server 展開のユーザーと共同作業できるようにするには、フェデレーションされたユーザーアクセスをサポートするために、少なくとも1つの外部アクセスポリシーを構成する必要があります。 詳しくは、「フェデレーションされた[ユーザーアクセスを制御するためのポリシーを構成する](../external-access-policies/configure-policies-to-control-federated-user-access.md)」をご覧ください。 特定のフェデレーションドメインへのアクセスを制御するには、「[許可された外部ドメインのサポートを構成](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)する」を参照してください。


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してフェデレーションおよびパブリック IM 接続を有効または無効にする

フェデレーションとパブリック IM 接続は、Windows PowerShell と CsAccessEdgeConfiguration コマンドレットを使用して管理することもできます。 このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 

## <a name="to-enable-federation-and-public-im-connectivity"></a>フェデレーションとパブリック IM 接続を有効にするには

  - フェデレーションとパブリック IM 接続を有効にするには、 **AllowFederatedUsers**プロパティの値を True ($True) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a>フェデレーションとパブリック IM 接続を無効にするには

  - フェデレーションとパブリック IM 接続を無効にするには、 **AllowFederatedUsers**プロパティの値を False ($False) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

