---
title: アーカイブ サーバーの関連付けの削除
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: アーカイブサーバーを削除するには、関連付けられているフロントエンドプール、フロントエンドサーバー、存続可能ブランチアプライアンス、および存続可能ブランチサーバーの依存関係を変更またはクリアする必要があります。 依存関係を削除するには、フロントエンドプール、フロントエンドサーバー、存続可能 Branch Appliance、存続可能 Branch Server の各プロパティを編集します。 依存関係をクリアし、トポロジビルダーでサーバーを削除すると、トポロジビルダー内の関連付けられたデータベースストアオブジェクトも削除されることが通知されます。
ms.openlocfilehash: bba21dadc70f5c9f62fea5073ef5bf815c8b35a1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752139"
---
# <a name="remove-the-archiving-server-association"></a>アーカイブ サーバーの関連付けの削除

アーカイブサーバーを削除するには、関連付けられているフロントエンドプール、フロントエンドサーバー、存続可能ブランチアプライアンス、および存続可能ブランチサーバーの依存関係を変更またはクリアする必要があります。 依存関係を削除するには、フロントエンドプール、フロントエンドサーバー、存続可能 Branch Appliance、存続可能 Branch Server の各プロパティを編集します。 トポロジビルダーで依存関係をクリアし、サーバーを削除すると、トポロジビルダー内の関連付けられたデータベースストアオブジェクトも削除されることが通知されます。
  
### <a name="to-remove-the-archiving-server-association"></a>アーカイブサーバーの関連付けを削除するには

1. Skype for Business Server 2019 フロントエンドサーバーで、トポロジビルダーを開きます。
    
2. 従来のインストールノードに移動します。
    
3. トポロジビルダーで、アーカイブサーバーが定義されている場所に応じて、 **Enterprise Edition フロントエンドプール**、 **Standard Edition フロントエンドサーバー**、または**ブランチサイト**を展開します。
    
4. 存続可能 Branch Server が関連付けられている場合は、[**ブランチサイト**] を展開し、[ブランチサイト] を展開して、[**存続可能ブランチアプライアンス**] を展開します。
    
    > [!NOTE]
    > ユーザーインターフェイスの**存続可能 Branch アプライアンス**は、存続可能 branch Server と存続可能 branch Appliance の両方に適用されます。 
  
5. アーカイブサーバーに関連付けられているプール、サーバー、またはデバイスを右クリックし、[**プロパティの編集**] をクリックします。
    
6. [**プロパティの編集**] の [**一般的な**関連付け] で、[  >  **Associations****アーカイブサーバーの関連付け**] チェックボックスをオフにして、[ **OK]** をクリックします。
    
7. 削除するアーカイブサーバーに関連付けられているその他のプール、サーバー、またはデバイスに対して、前の手順を繰り返します。
    
8. アーカイブサーバーを右クリックし、[**削除**] をクリックします。
    
9. [**依存ストアの削除**] で、[**OK**] をクリックします。
    
10. トポロジを公開し、レプリケーションの状態を確認してから、必要に応じて Skype for Business Server 展開ウィザードを実行します。 
    

