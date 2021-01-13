---
title: エッジ コンピューター設定エキスパンダー
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: エッジ サーバーのプール内にあるサーバーのプロパティを編集するには、次の操作を行います。
ms.openlocfilehash: 7c3b3d45617d8feeee062bb16e1c7222b71118d8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807127"
---
# <a name="edge-machine-settings-expander"></a>エッジ コンピューター設定エキスパンダー
 
エッジ サーバーのプール内にあるサーバーのプロパティを編集するには、次の操作を行います。
  
[**内部名または FQDN**] を変更するには、完全修飾ドメイン名 (FQDN) を編集します。FQDN が、ドメイン ネーム システム (DNS) ホスト (A) レコード、および内部エッジ ネットワーク インターフェイスのサーバーに割り当てられている証明書のサブジェクト名と一致している必要があります。[**内部 IP アドレス**] の値で、境界ネットワーク設定に関連して、内部ネットワークとして定義されたネットワーク インターフェイスに割り当てられる IP アドレスを定義します。
  
ダイアログの次の 3 つのセクションで、このエッジ サーバーの外部構成の IP アドレスを定義します。IP アドレスを変更できるかどうかは、エッジ サーバーのプール レベルでの [プロパティ] 設定の [**Web 会議と音声ビデオに対する別々の FQDN および IP アドレス設定の有効化**] の設定の影響を受けます。
  
## <a name="sip-access"></a>SIP アクセス

セッション開始プロトコル (SIP) アクセスのネットワーク インターフェイスに割り当てられている外部 IP アドレスを編集します。この IP アドレスは、パブリック IP アドレスまたはプライベート IP アドレス範囲内のアドレスのどちらにすることもできます。
  
> [!NOTE]
> プール設定ページの [**Web 会議と音声ビデオに個別の FQDN と IP アドレスを有効にする**] が有効になっている場合、SIP アクセスの IP アドレスのみ編集できます。
  
## <a name="web-conferencing"></a>Web 会議

Web 会議のネットワーク インターフェイスに割り当てられている外部 IP アドレスを編集します。この IP アドレスは、パブリック IP アドレスまたはプライベート IP アドレス範囲内のアドレスのどちらにすることもできます。
  
## <a name="audiovideo"></a>オーディオ/ビデオ

音声ビデオ (A/V) のネットワーク インターフェイスに割り当てられている外部 IP アドレスを編集します。この IP アドレスは、パブリック IP アドレスまたはプライベート IP アドレス範囲内のアドレスのどちらにすることもできます。
  
通常、[**NAT が有効な使用中のパブリック IP アドレス**] の設定は、音声ビデオ ネットワーク インターフェイスまたはエッジ サーバーの外部インターフェイスで使用されるパブリック アドレスです。[**Web 会議と音声ビデオに個別の FQDN と IP アドレスを有効にする**] が有効になっている場合、このパブリック IP アドレスが 3 つのすべての外部インターフェイスに使用されます。
  

