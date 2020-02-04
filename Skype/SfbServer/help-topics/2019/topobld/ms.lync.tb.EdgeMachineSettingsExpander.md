---
title: エッジ コンピューター設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
ROBOTS: NOINDEX, NOFOLLOW
description: エッジサーバーのプールにあるサーバーのプロパティを編集するには、次の操作を行います。
ms.openlocfilehash: 22f1e46481ce2392a806eadd6029ab51292d5585
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702292"
---
# <a name="edge-machine-settings-expander"></a>エッジ コンピューター設定エキスパンダー
 
エッジサーバーのプールにあるサーバーのプロパティを編集するには、次の操作を行います。
  
**内部名または fqdn**は、完全修飾ドメイン名 (fqdn) を編集することで変更できます。 FQDN は、ドメインネームシステム (DNS) host (A) レコードと、内部エッジネットワークインターフェイスに対してサーバーに割り当てられている証明書のサブジェクト名と一致する必要があります。 [**内部 ip アドレス**] の値は、境界ネットワーク設計を基準とした内部ネットワークとして定義されるネットワークインターフェイスに割り当てられている ip アドレスを定義します。
  
ダイアログの次の3つのセクションでは、このエッジサーバーの外部構成の IP アドレスを定義しています。 IP アドレスを変更できるかどうかは、この設定によって、エッジサーバープールレベルのプロパティ設定で、[ **web 会議に個別の FQDN と IP アドレスを有効にする] と [A/V** ] を設定することによって変わります。
  
## <a name="sip-access"></a>SIP アクセス

ネットワークインターフェイスに割り当てられている外部 IP アドレスをセッション開始プロトコル (SIP) アクセス用に編集します。 この IP アドレスは、パブリック IP アドレスまたはプライベート IP アドレス範囲内のアドレスのいずれかになります。
  
> [!NOTE]
> [ **Web 会議のために個別の FQDN と ip アドレスを有効にする] と**[プール設定] ページで [A/V] を有効にした場合、SIP アクセスの ip アドレスのみが編集可能になります。
  
## <a name="web-conferencing"></a>Web 会議

Web 会議用のネットワークインターフェイスに割り当てられている外部 IP アドレスを編集します。 この IP アドレスには、パブリック IP アドレス、またはプライベート IP アドレス範囲内のアドレスのいずれかを使うことができます。
  
## <a name="audiovideo"></a>音声/ビデオ

音声/ビデオ用のネットワークインターフェイス (A/V) に割り当てられている外部 IP アドレスを編集します。 この IP アドレスには、パブリック IP アドレス、またはプライベート IP アドレス範囲内のアドレスのいずれかを使うことができます。
  
[NAT を**有効にするパブリック IP アドレス**] の設定は、一般に、A/V ネットワークインターフェイスまたはエッジサーバーの外部インターフェイスで使用されるパブリックアドレスです。 この設定で**web 会議で個別の FQDN と IP アドレスを有効にし、A/V**を有効にした場合、このパブリック IP アドレスがすべての3つの外部インターフェイスで使用されます。
  

