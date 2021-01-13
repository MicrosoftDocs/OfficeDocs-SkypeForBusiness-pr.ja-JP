---
title: 外部アプリケーション全般設定エキスパンダー
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
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: 既に定義されている信頼済みアプリケーション サーバーのプロパティを編集するには、以下の操作を行います。
ms.openlocfilehash: 55f6bfee68370f8f341080e54953120e48f628f8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804767"
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

ドロップダウン リストから定義済みの Enterprise Edition フロントエンド プールまたは Standard Edition フロントエンド サーバーを選択して、信頼済みアプリケーション サーバー プールの次ホップ サーバーを指定できます。 ディレクターまたはディレクター プールは、信頼されたアプリケーション サーバーの次ホップとしては有効な選択肢ではないため、リストに表示されません。
  


**[OK] を** クリックして変更を受け入れて保存します。 変更を破棄してプロパティ ページを終了するには、**[キャンセル]** をクリックします。
  

