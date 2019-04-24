---
title: フェデレーション パートナーに対するアーカイブ免責事項の送信の有効化または無効化
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 859b4e295a90fd44ce69efe4af7daa63ddc8812c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197864"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>ビジネス サーバーの Skype でのフェデレーション パートナーにアーカイブについての免責事項の送信を無効にするを有効または

時に、エッジ サーバーの展開し、フェデレーションを有効になっている組織では、必要がありますが指定されて自動的にフェデレーション パートナーにアーカイブについての免責事項を送信するかどうか。 外部通信をアーカイブする場合は、アーカイブの免責事項の送信を有効にする必要があります。 その構成を変更するのにはこのトピックの手順を使用します。

> [!NOTE]
> 次の手順では、組織のフェデレーションが既に有効にことを前提としています。 フェデレーションを有効にする方法の詳細[を有効にするかリモート ユーザー アクセスを無効にする](enable-or-disable-remote-user-access.md)を参照してください。


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>有効にするか、フェデレーション パートナーへのアーカイブの免責事項の送信を無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション ・ バーで [**外部ユーザー アクセス**] をクリックして、[**アクセス エッジ構成**] をクリックします。

4.  [**アクセス エッジ構成**] タブで、[**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。

5.  **アクセス エッジ構成の編集**、**フェデレーション ユーザーとの通信を有効にする**には、オンまたはオフに、**アーカイブ、フェデレーション パートナーへの免責事項を送信**するチェック ボックスを有効にするか、アーカイブを自動的に送信を無効にします。免責事項です。

6.  [**コミット**] をクリックします。

フェデレーション ユーザーにビジネスのサーバーの展開に、Skype のユーザーと共同作業を有効にするには、必要がありますもしているフェデレーション ユーザー アクセスをサポートするために少なくとも 1 つの外部アクセス ポリシーです。 特定のフェデレーション ドメインのアクセスを制御する方法の詳細は、[許可された外部ドメインのサポートを構成する](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)を参照してください。


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>有効にするか、Windows PowerShell コマンドレットを使用して、アーカイブの免責事項を無効にします。

アーカイブについての免責事項の使用は、Windows PowerShell とセット CsAccessEdgeConfiguration コマンドレットを使用して管理できます。 ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。 

## <a name="to-enable-the-archiving-disclaimer"></a>アーカイブについての免責事項を有効にするには

  - アーカイブについての免責事項を有効にするには、**EnableArchivingDisclaimer** プロパティの値を True ($True) に設定します。
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>アーカイブについての免責事項を無効にするには

  - アーカイブについての免責事項を無効にするには、**EnableArchivingDisclaimer** プロパティの値を False ($False) に設定します。
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


