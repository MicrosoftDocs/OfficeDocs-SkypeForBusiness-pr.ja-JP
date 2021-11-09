---
title: 外部アプリケーション全般設定エキスパンダー
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: 既に定義されている信頼済みアプリケーション サーバーのプロパティを編集するには、以下の操作を行います。
ms.openlocfilehash: d003a14506ef34f8e37778ec8dd262e269ed93a9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860334"
---
# <a name="external-application-general-settings-expander"></a>外部アプリケーション全般設定エキスパンダー
 
既に定義されている信頼済みアプリケーション サーバーのプロパティを編集するには、以下の操作を行います。
  
更新できるセクションは以下の 2 つです。
  
> 全般設定
> 
> 次ホップ設定
    
## <a name="general-settings"></a>全般設定

信頼されたアプリケーション サーバー プールの現在の完全修飾ドメイン名 (FQDN) を変更できます。プールの FQDN の名前を編集します。クライアントまたはサーバーが新しいプール名に接続できるようにするには、新しいエントリのドメイン ネーム システム (DNS) ホスト (A) のレコードが存在する必要があります。
  
このプールへの構成データのレプリケーションが必要な場合は、[**このプールへの構成データのレプリケーションを有効にする**] をオンにします。構成データをレプリケーションしない場合は、このチェック ボックスをオフにします。
  
## <a name="next-hop-settings"></a>次ホップ設定

信頼できるアプリケーション サーバー プールの次ホップ サーバーを指定するには、定義済みの Enterprise Edition フロントエンド プールまたは Standard Edition フロント エンド サーバーをドロップダウン リストから選択します。 ディレクターまたはディレクター プールは、信頼されたアプリケーション サーバーの次ホップとしては有効な選択肢ではないため、リストに表示されません。
  


**[OK] を** クリックして変更を受け入れて保存します。 変更を破棄してプロパティ ページを終了するには、**[キャンセル]** をクリックします。
  

