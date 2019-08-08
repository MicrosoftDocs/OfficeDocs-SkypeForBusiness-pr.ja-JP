---
title: Skype for Business Server の通話受付制御の展開の最終チェックリスト
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Skype for Business Server Enterprise Voice で通話受付制御 (CAC) を展開するための最終チェックリスト。
ms.openlocfilehash: 275afdfcb3c5e2b7cc635e073bcb5b9ba5edc853
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240318"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>通話受付制御の展開: Skype for Business Server の最終チェックリスト
 
Skype for Business Server Enterprise Voice で通話受付制御 (CAC) を展開するための最終チェックリスト。 
  
次のチェック リストを使用して、通話受付管理サービス (CAC) を展開するために必要なすべての構成タスクを完了したことを確認してください。
  
- 1つ以上のエッジサーバーが展開されている場合、各外部インターフェイス IP アドレスは、ネットワーク構成設定のサブネットリストに追加する必要があります。この場合、ビットマスクは32になります。 音声ビデオ エッジ サービスが展開されている地理的な場所のネットワーク サイト ID にこのサブネット (IP アドレス) を関連付ける必要もあります。
    
    > [!NOTE]
    > CAC を実装するためにエッジサーバーは必要ありません。 
  
- 「 [Skype For Business Server で通話受付制御を有効にする](enable-call-admission-control.md)」で指定されているように、CAC が有効になっていることを確認します。
    
- すべてのセントラル サイトで CAC が有効化されていることを確認します。 これは、トポロジビルダーで行うことができます。 公開時に警告が生成された場合は、無視しない*で*ください。
    
- エンタープライズ ネットワークで管理されているすべてのサブネットがネットワーク構成設定で構成されていることを確認します。 また、「 [Skype For business でのネットワーク領域、サイト、サブネットの展開](deploy-network.md)」で説明されているように、すべてのサブネットがネットワークサイトに関連付けられていることも重要です。
    
- すべてのフロントエンド サーバー、存続可能ブランチ アプライアンス (SBA)、音声ビデオ会議サーバー (別プールの場合)、および仲介サーバーのサブネットまたは IP アドレスがネットワーク構成設定で構成されていることを確認します。
    

