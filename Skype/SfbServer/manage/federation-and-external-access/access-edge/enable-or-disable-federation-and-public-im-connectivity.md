---
title: フェデレーションおよびパブリック IM 接続の有効化または無効化
ms.reviewer: ''
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: フェデレーションとは、パートナーのドメインとユーザーのインスタント メッセージング (IM) プロバイダー ユーザーのユーザーと共同作業をサポートしているの公開を含め、信頼された顧客またはパートナー組織のアカウントを持つユーザーを有効にするのに必要なサポート、組織です。
ms.openlocfilehash: c207f409164162f066d1ea49197cbd26fa50273b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199935"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a>有効にするか、ビジネスのサーバーのフェデレーションと Skype でのパブリック IM 接続を無効にします。

フェデレーションとは、パートナーのドメインとユーザーのインスタント メッセージング (IM) プロバイダー ユーザーのユーザーと共同作業をサポートしているの公開を含め、信頼された顧客またはパートナー組織のアカウントを持つユーザーを有効にするのに必要なサポート、組織です。 フェデレーションがホストされている Exchange サービス プロバイダーを使用して、ボイス メールを Microsoft Exchange Online のようにホストされている Exchange サービスのメールボックスがあるエンタープライズ VoIP ユーザーに提供するためにも必要です。 これらの外部ドメインとの信頼関係が確立されると、アクセス、展開するために Skype のビジネス サーバー間の通信をそれらのドメイン内のユーザーを認証できます。 この信頼関係は連合と呼ばれ、または依存している Active Directory の信頼関係は関係ありません。

フェデレーション ドメインのユーザーによるアクセスをサポートするには、フェデレーションを有効にする必要があります。 組織のフェデレーションを有効にした場合は、次のオプションを実装するかどうかとして指定する必要があります。

  - **パートナー ドメインの検出を有効にする**   このオプションを有効にすると、Business Server の Skype を使ってドメイン ネーム システム (DNS) レコード一覧に表示されない許可するドメイン] ボックスの一覧から自動的に評価の着信トラフィックが検出されたドメインを検出しようとしています。フェデレーション パートナーとの制限または信頼レベルは、トラフィック量の管理者の設定に基づいて、トラフィックをブロックします。 このオプションをオフにすると、フェデレーション ユーザーのアクセスは許可するドメイン] ボックスの一覧に含まれているドメインのユーザーに対してのみ有効です。 このオプションを選択するかどうかは、その個人を指定することをブロックまたは許可されているドメイン フェデレーション ドメインのアクセス エッジ サービスを実行して特定のサーバーにアクセスを制限することです。 フェデレーション ドメインによるアクセスの制御に関する詳細については、[許可された外部ドメインのサポートを構成する](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)を参照してください。

  - **フェデレーション パートナーにアーカイブの免責事項を送信する**   展開でアーカイブが設定されているフェデレーション パートナーに免責事項の通知が送信されます。 フェデレーション パートナーのドメインとの外部通信のアーカイブをサポートする場合、アーカイブについての免責事項パートナーに通知のメッセージがアーカイブされることを有効にする必要があります。

後で、一時的または恒久的には、フェデレーション ドメインのユーザーによるアクセスを防ぐために必要があると、組織のフェデレーションを無効にできます。 このセクションでを有効にするか、組織をサポートする適切なフェデレーション オプションを指定するなど、組織のフェデレーション ユーザー アクセスを無効にする手順を使用します。

> [!NOTE]  
> アクセス エッジ サービスを実行しているサーバーがフェデレーション ドメインへのルーティングをサポートする指定のみ、組織のフェデレーションを有効にするとします。 フェデレーション ドメイン内のユーザーは、フェデレーション ユーザー アクセスをサポートするために少なくとも 1 つのポリシーを構成するまでに、IM または組織内の会議に参加できません。 パブリック IM サービス プロバイダーのユーザーは、パブリック IM 接続をサポートするために少なくとも 1 つのポリシーを構成するまで、IM または組織内の会議に参加できません。 ビジネス サーバーの Skype までは使用できません通話応答、Outlook Voice Access のボイス メールを提供するホストされた Exchange サービスまたはユーザーのメールボックスの自動応答サービス ホストされている Exchange サービスにホストされている音声を構成します。ポリシー ルーティング情報を提供します。 他の組織のフェデレーション ドメインのユーザーとの通信用のポリシーを構成する詳細については、[組織のドメインをフェデレーションする SIP の管理](../sip-domains/manage-sip-federated-domains-for-your-organization.md)を参照してください。 さらに、IM サービス プロバイダーのユーザーとの通信をサポートする場合は、サポートし、もサポートする個々 のサービス プロバイダーのサポートを構成するポリシーを構成する必要があります。 詳細については、[組織のプロバイダーをフェデレーションする SIP 管理](../sip-providers/manage-sip-federated-providers-for-your-organization.md)を参照してください。


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>有効にするか、組織のフェデレーション ユーザー アクセスを無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション ・ バーでは、**外部ユーザー アクセス**をクリックし、**アクセス エッジの構成**] をクリックします。

4.  [**アクセス エッジ構成**] ページで、[**グローバル**] をクリック**を編集**するには、、[**詳細の表示**] をクリックします。

5.  **アクセス エッジ構成の編集**] で、次のいずれかの操作を行います。
    
      - 組織のフェデレーション ユーザー アクセスを有効にするには、**フェデレーション ユーザーとの通信を有効にする**] チェック ボックスを選択します。
    
      - 組織のフェデレーション ユーザー アクセスを無効にするには、**フェデレーション ユーザーとの通信を有効にする**] チェック ボックスをオフにします。

6.  **フェデレーション ユーザーとの通信を有効にする**] チェック ボックスを選択した場合は、次の操作を行います。
    
    1.  パートナー ドメインの自動検出をサポートする場合は、**パートナー ドメインの検出を有効にする**] チェック ボックスを選択します。
    
    2.  組織は、外部通信のアーカイブをサポートする場合は、**アーカイブ、フェデレーション パートナーへの免責事項の送信**] チェック ボックスを選択します。

7.  [**コミット**] をクリックします。

フェデレーション ユーザーにビジネスのサーバーの展開に、Skype のユーザーと共同作業を有効にするには、フェデレーション ユーザー アクセスをサポートするために少なくとも 1 つの外部アクセス ポリシーを構成することもあります。 詳細については、[制御するポリシーを構成するユーザーのアクセスをフェデレーションする](../external-access-policies/configure-policies-to-control-federated-user-access.md)を参照してください。 特定のフェデレーション ドメインのアクセスを制御するには、[許可された外部ドメインのサポートを構成する](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)を参照してください。


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>有効にするか、Windows PowerShell コマンドレットを使用してフェデレーションとパブリック IM 接続を無効にします。

Windows PowerShell とセット CsAccessEdgeConfiguration コマンドレットを使用しては、フェデレーションとパブリック IM 接続を管理することもできます。 ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。 

## <a name="to-enable-federation-and-public-im-connectivity"></a>フェデレーションとパブリック IM 接続を有効にするには

  - フェデレーションとパブリック IM 接続を有効にするには、 **AllowFederatedUsers**プロパティの値を True ($True) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a>フェデレーションとパブリック IM 接続を無効にするには

  - フェデレーションとパブリック IM 接続を無効にするには、False ($False) に**AllowFederatedUsers**プロパティの値を設定します。
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

