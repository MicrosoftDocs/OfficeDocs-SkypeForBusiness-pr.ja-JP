---
title: エッジのマシンの設定の拡張
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
ROBOTS: NOINDEX, NOFOLLOW
description: エッジ サーバーのプール内のサーバーのプロパティを編集するには、次の操作を行います。
ms.openlocfilehash: d0df347d3432d28b6d5f1df9d32cb4cd4f4423cd
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21057259"
---
# <a name="edge-machine-settings-expander"></a>エッジのマシンの設定の拡張
 
エッジ サーバーのプール内のサーバーのプロパティを編集するには、次の操作を行います。
  
**内部名または FQDN**は、完全修飾ドメイン名 (FQDN) を編集することによって変更できます。 FQDN は、ドメイン ネーム システム (DNS) ホスト (a) レコード、および内部の境界ネットワーク インターフェイスのサーバーに割り当てられている証明書のサブジェクト名と一致する必要があります。 **内部 IP アドレス**の値は、内部ネットワーク、境界ネットワークの設計を基準として定義されているネットワーク ・ インタ フェースに割り当てられている IP アドレスを定義します。
  
ダイアログ ボックスの次の 3 つのセクションでは、このエッジ サーバーの外部構成の IP アドレスを定義します。 設定で IP アドレスを変更する機能が影響を受ける**を有効にする別の FQDN と IP アドレスの web 会議および A/V**プール レベルのエッジ サーバーでプロパティの設定に。
  
## <a name="sip-access"></a>SIP アクセス

セッション開始プロトコル (SIP) アクセス用のネットワーク インターフェイスに割り当てられている外部 IP アドレスを編集します。 この IP アドレスは IP アドレスをパブリックまたはプライベート IP アドレスの範囲内のアドレスのいずれかできます。
  
> [!NOTE]
> 場合設定**を有効にする別の FQDN と IP アドレスの web 会議および A/V**プールの設定] ページが有効なだけで SIP アクセス用の IP アドレスを編集可能になります。
  
## <a name="web-conferencing"></a>Web 会議

Web 会議のネットワーク インターフェイスに割り当てられている外部 IP アドレスを編集します。 この IP アドレスには、パブリック IP アドレスまたはプライベート IP アドレスの範囲内のアドレスのいずれかを指定できます。
  
## <a name="audiovideo"></a>オーディオ/ビデオ

オーディオとビデオのネットワーク インターフェイスに割り当てられている外部 IP アドレスの編集 (A/V)。 この IP アドレスには、パブリック IP アドレスまたはプライベート IP アドレスの範囲内のアドレスのいずれかを指定できます。
  
**NAT には、使用するパブリック IP アドレスが有効になっている**は、どちらか A の外部インターフェイスで使用されるパブリック アドレス V インターフェイスまたはエッジ サーバーの一般的なネットワークです。 場合設定**を有効にする別の FQDN と IP アドレスの web 会議および A/V**が有効にすると、このパブリック IP アドレスがすべての 3 つの外部インターフェイスの使用します。
  

