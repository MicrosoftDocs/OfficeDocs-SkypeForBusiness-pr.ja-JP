---
title: Skype for Business Server の通話受付管理展開の最終チェックリスト
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Skype for Business Server サービスに通話受付管理 (CAC) を展開するための最終チェックリストエンタープライズ VoIP。
ms.openlocfilehash: d3a6484e35225627c8f22002823eff7fd5939694
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830837"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>通話受付管理の展開: Skype for Business Server の最終チェックリスト
 
Skype for Business Server サービスに通話受付管理 (CAC) を展開するための最終チェックリストエンタープライズ VoIP。 
  
次のチェックリストを使用して、通話受付管理 (CAC) を展開するために必要なすべての構成タスクが完了したのを確認します。
  
- 1 つまたは複数のエッジ サーバーが展開されている場合には、32 ビット マスクのすべての外部インターフェイス IP アドレスがネットワーク構成設定のサブネット リストに追加されている必要があります。音声ビデオ エッジ サービスが展開されている地理的な場所のネットワーク サイト ID にこのサブネット (IP アドレス) を関連付ける必要もあります。
    
    > [!NOTE]
    > CAC を実装するためにエッジ サーバーは必要ありません。 
  
- 「Skype for Business Server で通話受付管理を有効にする」で指定されている CAC [が有効になっている必要があります](enable-call-admission-control.md)。
    
- すべてのセントラル サイトで CAC が有効化されていることを確認します。 これは、トポロジ ビルダーを使用して行います。 発行時に警告が生成された場合は  *、無視*  しない。
    
- エンタープライズ ネットワークで管理されているすべてのサブネットがネットワーク構成設定で構成されていることを確認します。 また [、「Skype for Business](deploy-network.md)でのネットワーク地域、サイト、サブネットの展開」で説明したように、すべてのサブネットをネットワーク サイトに関連付けることです。
    
- すべてのフロントエンド サーバー、存続可能ブランチ アプライアンス (SBA)、音声ビデオ会議サーバー (別プールの場合)、および仲介サーバーのサブネットまたは IP アドレスがネットワーク構成設定で構成されていることを確認します。
    

