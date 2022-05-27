---
title: フェデレーションおよびパブリック IM 接続の有効化または無効化
ms.reviewer: ''
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
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
description: 信頼できる顧客またはパートナー組織のアカウントを持つユーザー (パートナー ドメイン、サポートするパブリック インスタント メッセージング (IM) プロバイダー ユーザーなど) が組織内のユーザーと共同作業できるようにするには、フェデレーションのサポートが必要です。
ms.openlocfilehash: 0b78eacd473422c204f8614464b406657f3dc92b
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675749"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a>Skype for Business Serverでフェデレーションとパブリック IM 接続を有効または無効にする

信頼できる顧客またはパートナー組織のアカウントを持つユーザー (パートナー ドメイン、サポートするパブリック インスタント メッセージング (IM) プロバイダー ユーザーなど) が組織内のユーザーと共同作業できるようにするには、フェデレーションのサポートが必要です。 フェデレーションでは、ホストされているExchange サービス プロバイダーを使用して、メールボックスがホストされているExchange サービス (Microsoft Exchange Online など) にあるエンタープライズ VoIP ユーザーにボイス メールを提供する必要もあります。 これらの外部ドメインとの信頼関係を確立したら、これらのドメイン内のユーザーが展開にアクセスし、Skype for Business Server通信に参加することを承認できます。 この信頼関係はフェデレーションと呼ばれ、Active Directory の信頼関係に関連したり依存したりしません。

フェデレーション ドメインのユーザーによるアクセスをサポートするには、フェデレーションを有効にする必要があります。 組織に対してフェデレーションを有効にする場合、次のオプションを実装するかどうかも指定する必要があります。

  - **パートナー ドメイン検出を有効にする**  このオプションを有効にした場合、Skype for Business Serverはドメイン ネーム システム (DNS) レコードを使用して、許可されたドメインの一覧に表示されていないドメインの検出を試み、検出されたフェデレーション パートナーからの受信トラフィックを自動的に評価し、信頼レベル、トラフィック量、および管理者設定に基づいてそのトラフィックを制限またはブロックします。 このオプションを無効にすると、フェデレーション ユーザーは、許可済みのドメイン一覧に含めたドメインのユーザーにしか、アクセスできません。 このオプションの有効、無効にかかわらず、フェデレーション ドメイン内のアクセス エッジ サービスを実行する特定のサーバーへのアクセスを制限するなど、個々のドメインを禁止するか許可するかを指定できます。 フェデレーション ドメインによるアクセスの制御の詳細については、「 [許可された外部ドメインのサポートを構成する」を](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)参照してください。

  - [**フェデレーション パートナーにアーカイブについての免責事項を送信する**]: 展開でアーカイブが準備されていることを示す免責事項通知がフェデレーション パートナーに送信されます。フェデレーション パートナー ドメインとの外部通信のアーカイブをサポートする場合は、アーカイブの免責事項の通知を有効にして、メッセージがアーカイブされることをパートナーに通知する必要があります。

後でフェデレーション ドメイン ユーザーからのアクセスを一時的または永久に禁止する場合は、組織に対するフェデレーションを無効にできます。組織でサポートする適切なフェデレーション オプションを指定するなど、組織に対するフェデレーション ユーザーのアクセスを有効または無効にするには、このセクションの手順を使用します。

> [!NOTE]  
> 組織に対してフェデレーションを有効にしても、アクセス エッジ サービスを実行するサーバーで、フェデレーション ドメイン宛てのルーティングをサポートすることを指定するだけです。 フェデレーション ユーザー アクセスをサポートするポリシーを少なくとも 1 つ構成するまでは、フェデレーション ドメインのユーザーは、組織の会議や IM に参加できません。 パブリック IM 接続をサポートするポリシーを少なくとも 1 つ構成するまでは、パブリック IM サービス プロバイダーのユーザーも、組織の会議や IM に参加できません。 Skype for Business Server、ホストされているExchange サービスを使用して、ルーティングを提供するホストボイス メール ポリシーを構成するまで、メールボックスがホストされたExchange サービス上にあるユーザーの通話応答、Outlook Voice Access (ボイス メールを含む)、または自動応答サービスを提供することはできません。情報。 他の組織のフェデレーション ドメインのユーザーと通信するためのポリシーの構成の詳細については、「組織の [SIP フェデレーション ドメインの管理](../sip-domains/manage-sip-federated-domains-for-your-organization.md)」を参照してください。 さらに、IM サービス プロバイダーのユーザーとの通信をサポートする場合は、これをサポートするポリシーを構成し、サポートする個々のサービス プロバイダーのサポートも構成する必要があります。 詳細については、「   [組織の SIP フェデレーション プロバイダーの管理」を参照してください](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>組織に対するフェデレーション ユーザー アクセスを有効または無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理 URL を入力してSkype for Business Server コントロール パネルを開きます。 

3.  左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。

4.  [**アクセス エッジ構成**] ページで、[**グローバル**]、[**編集**]、[**詳細の表示**] の順にクリックします。

5.  [**アクセス エッジ構成の編集**] で、次のどちらかの操作を行います。
    
      - 組織に対してフェデレーション ユーザー アクセスを有効にするには、[**フェデレーション ユーザーとの通信を有効にする**] チェック ボックスをオンにします。
    
      - 組織に対してフェデレーション ユーザー アクセスを無効にするには、[**フェデレーション ユーザーとの通信を有効にする**] チェック ボックスをオフにします。

6.  [**フェデレーション ユーザーとの通信を有効にする**] チェック ボックスをオンにした場合は、次を実行します。
    
    1.  パートナー ドメインの自動検出をサポートする場合は、[**パートナー ドメインの検出を有効にする**] チェック ボックスをオンにします。
    
    2.  組織で外部通信のアーカイブをサポートする場合は、[**フェデレーション パートナーにアーカイブについての免責事項を送信する**] チェック ボックスをオンにします。

7.  [**確定**] をクリックします。

フェデレーション ユーザーがSkype for Business Serverデプロイ内のユーザーと共同作業できるようにするには、フェデレーション ユーザー アクセスをサポートするように少なくとも 1 つの外部アクセス ポリシーを構成する必要もあります。 詳細については、「 [フェデレーション ユーザー アクセスを制御するポリシーを構成する](../external-access-policies/configure-policies-to-control-federated-user-access.md)」を参照してください。 特定のフェデレーション ドメインのアクセスを制御するには、「 [許可された外部ドメインのサポートを構成する」を](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)参照してください。


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用したフェデレーションとパブリック IM 接続の有効化または無効化

フェデレーションとパブリック IM 接続は、Windows PowerShellとSet-CsAccessEdgeConfigurationコマンドレットを使用して管理することもできます。 このコマンドレットは、Skype for Business Server管理シェルから実行することも、Windows PowerShellのリモート セッションから実行することもできます。 

## <a name="to-enable-federation-and-public-im-connectivity"></a>フェデレーションとパブリック IM 接続を有効にするには

  - フェデレーションとパブリック IM 接続を有効にするには、**AllowFederatedUsers** プロパティの値を True ($True) に設定します。<br/><br/>Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a>フェデレーションとパブリック IM 接続を無効にするには

  - フェデレーションとパブリック IM 接続を無効にするには、**AllowFederatedUsers** プロパティの値を False ($False) に設定します。<br/><br/>Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

