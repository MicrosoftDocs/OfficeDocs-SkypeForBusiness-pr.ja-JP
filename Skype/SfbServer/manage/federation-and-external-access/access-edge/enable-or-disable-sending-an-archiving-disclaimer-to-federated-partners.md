---
title: フェデレーション パートナーに対するアーカイブ免責事項の送信の有効化または無効化
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: サーバー内のフェデレーション パートナーにアーカイブの免責事項を送信するSkype for Business Server。
ms.openlocfilehash: cbdfe6a53df73c5af3ef8d4b07b1bd2a4fc27a0a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861354"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>アーカイブに関する免責事項をフェデレーション パートナーに送信する機能を有効または無効Skype for Business Server

エッジ サーバーを展開し、組織に対してフェデレーションを有効にした時点で、フェデレーション パートナーにアーカイブについての免責事項を自動で送信するかどうかを指定する必要があります。 外部通信をアーカイブする場合は、アーカイブについての免責事項の送信を有効にする必要があります。 このトピックの手順を使用して、この構成を変更します。

> [!NOTE]
> 次の手順では、既に組織に対してフェデレーションを有効にしていることを前提としています。 フェデレーションの有効化の詳細については、「リモート ユーザー アクセス [を有効または無効にする」を参照してください](enable-or-disable-remote-user-access.md)。


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>フェデレーション パートナーへのアーカイブ免責事項の送信を有効または無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 

3.  左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。

4.  [**アクセス エッジ構成**] タブで、[**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。

5.  [**アクセス エッジ構成の編集**] の [**フェデレーション ユーザーとの通信を有効にする**] で、[**フェデレーション パートナーにアーカイブについての免責事項を送信する**] チェック ボックスをオンまたはオフにして、アーカイブについての免責事項の自動送信を有効または無効にします。

6.  [**確定**] をクリックします。

フェデレーション ユーザーが Skype for Business Server 展開でユーザーと共同作業を行う場合は、フェデレーション ユーザー アクセスをサポートするように少なくとも 1 つの外部アクセス ポリシーも構成している必要があります。 特定のフェデレーション ドメインのアクセス制御の詳細については、「許可された外部ドメインのサポートを構成 [する」を参照してください](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用してアーカイブの免責事項を有効またはWindows PowerShellする

アーカイブに関する免責事項の使用は、Windows PowerShellコマンドレットをSet-CsAccessEdgeConfigurationできます。 このコマンドレットは、管理シェルから、またはSkype for Business Serverのリモート セッションから実行Windows PowerShell。 

## <a name="to-enable-the-archiving-disclaimer"></a>アーカイブの免責事項を有効にするには

  - アーカイブについての免責事項を有効にするには、**EnableArchivingDisclaimer** プロパティの値を True ($True) に設定します。<br/><br/>Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>アーカイブの免責事項を無効にするには

  - アーカイブについての免責事項を有効にするには、**EnableArchivingDisclaimer** プロパティの値を False ($False) に設定します。<br/><br/>Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

