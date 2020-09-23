---
title: 外部アプリケーション全般設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: 既に定義されている信頼済みアプリケーション サーバーのプロパティを編集するには、以下の操作を行います。
ms.openlocfilehash: 9a9ed62040724d08ebcd711551cd1ce6e831d683
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218138"
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

信頼済みアプリケーションサーバープールの次ホップサーバーを指定するには、定義済みの Enterprise Edition フロントエンドプールまたは Standard Edition フロントエンドサーバーをドロップダウンリストから選択します。 ディレクターまたはディレクター プールは、信頼されたアプリケーション サーバーの次ホップとしては有効な選択肢ではないため、リストに表示されません。
  


[ **OK]** をクリックして変更を受け入れ、保存します。 変更を破棄してプロパティ ページを終了するには、**[キャンセル]** をクリックします。
  

