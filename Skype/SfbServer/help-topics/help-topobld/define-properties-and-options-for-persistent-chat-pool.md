---
title: 常設チャット プールのプロパティとオプションの定義
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 永続的なチャット サーバーまたは永続的なチャット サーバー プールのオプションを構成するには、次のプロパティを定義します。
ms.openlocfilehash: 380a1e34e041368d4520cd5c8ecea5b18284ef51
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887544"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>常設チャット プールのプロパティとオプションの定義
 
永続的なチャット サーバーまたは永続的なチャット サーバー プールのオプションを構成するには、次のプロパティを定義します。
  
 **永続的なチャット プールの表示名**: この永続的なチャット サーバーまたは永続的なチャット サーバー プールに表示されるユーザー フレンドリ名を定義する必要なプロパティです。
  
 **永続的なチャットのポート**: ポートを定義する必要なプロパティ番号を永続的なチャット サーバーまたはプールの永続的なチャット サーバー上でリッスンします。
  
 **コンプライアンスを有効にする**: の導入し、省略可能な永続的なチャットのコンプライアンス機能とデータベースを実装する場合はチェック ボックスをオンにします。
  
 **災害復旧を有効にする SQL Server のバックアップの使用を格納**します。 から別の SQL Server 上のストアの構成のバックアップ セットを展開し、永続的なチャットの SQL Server の災害復旧を実装する場合、このチェック ボックスを保存] を選択します。 詳細については、[構成の高可用性とビジネス サーバー 2015 の Skype での永続的なチャット サーバーの障害回復](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)を参照してください。
  
> [!NOTE]
> このオプションは、複数のサーバーで構成されたプールに対してのみ使用できます。 
  
 **サイトの既定値としてこのプールを使用して\<では、このサーバーまたはプールを構成しているサイト\>**: このチェック ボックスをオンに、既定の永続的なチャット サーバーまたはサイトの永続的なチャット サーバー プールになります。 サイトごと、1 つの既定の永続的なチャット サーバーまたは pol をすることが必要です。
  
> [!NOTE]
> トポロジに複数のサイトが含まれる場合は、[**このプールをすべてのサイトの既定プールとして使う**] チェック ボックスも表示されます。
  
前のプール定義ダイアログに戻るには、[**戻る**] をクリックします。
  
永続的なチャット サーバー プールの定義を続行するには、このプールのオプションの入力が終了したら**次へ**をクリックします。
  
すべての変更を破棄して**新しい常設チャット プールの定義**ウィザードを終了するには、[**キャンセル**] をクリックします。
  
このページのような状況依存のヘルプにアクセスするには、[**ヘルプ**] をクリックします。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 の常設チャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[ビジネス サーバー 2015 トポロジの場合、Skype に永続的なチャット サーバーを追加します。](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
