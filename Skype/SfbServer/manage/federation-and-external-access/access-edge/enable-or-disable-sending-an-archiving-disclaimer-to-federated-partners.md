---
title: フェデレーション パートナーに対するアーカイブ免責事項の送信の有効化または無効化
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: c2f64a617cae938ffe64ec8db313402785413c49
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280216"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>Skype for Business Server でフェデレーションパートナーへのアーカイブの免責事項の送信を有効または無効にする

エッジサーバーを展開して組織のフェデレーションを有効にした時点で、アーカイブの免責事項をフェデレーションパートナーに自動的に送信するかどうかを指定する必要があります。 外部通信をアーカイブする場合は、アーカイブの免責事項の送信を有効にする必要があります。 この設定を変更するには、このトピックの手順を使用します。

> [!NOTE]
> 次の手順では、組織のフェデレーションを既に有効にしていることを前提としています。 フェデレーションを有効にする方法について詳しくは、「[リモートユーザーアクセスを有効または無効](enable-or-disable-remote-user-access.md)にする」をご覧ください。


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>フェデレーションパートナーへのアーカイブの免責事項の送信を有効または無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。 

3.  左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**アクセスエッジ構成**] をクリックします。

4.  [**アクセス エッジ構成**] タブで、[**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。

5.  [ **Access Edge 構成の編集**] の [**フェデレーションユーザーとの通信を有効**にする] で、[アーカイブの**免責事項をフェデレーションパートナーに送信**する] チェックボックスをオンまたはオフにして、アーカイブの自動送信を有効または無効にします。契約.

6.  [**コミット**] をクリックします。

フェデレーションされたユーザーが Skype for Business Server 展開のユーザーと共同作業できるようにするには、フェデレーションされたユーザーアクセスをサポートするために、少なくとも1つの外部アクセスポリシーを構成しておく必要があります。 特定のフェデレーションドメインのアクセス制御の詳細については、「許可されている[外部ドメインのサポートを構成する](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)」を参照してください。


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してアーカイブ免責事項を有効または無効にする

アーカイブ免責事項の使用は、Windows PowerShell と CsAccessEdgeConfiguration コマンドレットを使用して管理できます。 このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 

## <a name="to-enable-the-archiving-disclaimer"></a>アーカイブの免責事項を有効にするには

  - アーカイブについての免責事項を有効にするには、**EnableArchivingDisclaimer** プロパティの値を True ($True) に設定します。
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>アーカイブの免責事項を無効にするには

  - アーカイブについての免責事項を無効にするには、**EnableArchivingDisclaimer** プロパティの値を False ($False) に設定します。
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


