---
title: アーカイブ サーバーの関連付けの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: アーカイブサーバーを削除するには、関連するフロントエンドプール、フロントエンドサーバー、Survivable Branch Appliance、および Survivable Branch Server の依存関係を変更またはクリアする必要があります。 フロントエンドプール、フロントエンドサーバー、Survivable Branch Appliance、Survivable Branch Server のプロパティを編集して、依存関係を削除します。 依存関係を消去して、トポロジビルダーでサーバーを削除すると、トポロジビルダーの関連付けられたデータベースストアオブジェクトも削除されることが通知されます。
ms.openlocfilehash: d6d7b7f53f9997b17893db079090e1837ce77f4d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244185"
---
# <a name="remove-the-archiving-server-association"></a>アーカイブ サーバーの関連付けの削除

アーカイブサーバーを削除するには、関連付けられたフロントエンドプール、フロントエンドサーバー、Survivable Branch Appliance、Survivable Branch Server の依存関係を変更またはクリアする必要があります。 フロントエンドプール、フロントエンドサーバー、Survivable Branch Appliance、Survivable Branch Server のプロパティを編集して、依存関係を削除します。 [トポロジビルダー] で、依存関係を消去してサーバーを削除すると、関連付けられているデータベースストアオブジェクトもトポロジビルダーで削除されることが通知されます。
  
### <a name="to-remove-the-archiving-server-association"></a>アーカイブサーバーの関連付けを削除するには

1. Skype for Business Server 2019 フロントエンドサーバーで、[トポロジビルダー] を開きます。
    
2. 従来のインストールノードに移動します。
    
3. [トポロジビルダー] で、アーカイブサーバーが定義されている場所に応じて、[ **Enterprise Edition フロントエンドプール**]、[ **Standard Edition フロントエンドサーバー**]、または [**ブランチサイト**] を展開します。
    
4. Survivable Branch Server が関連付けられている場合は、[**ブランチサイト**] を展開し、[ブランチサイト名] を展開して、[ **Survivable branch アプライアンス**] を展開します。
    
    > [!NOTE]
    > ユーザーインターフェイス内の**Survivable Branch アプライアンス**は、Survivable branch Server と Survivable branch Appliance の両方に適用されます。 
  
5. アーカイブサーバーに関連付けられているプール、サーバー、またはデバイスを右クリックし、[**プロパティの編集**] をクリックします。
    
6. [**プロパティの編集**] の [**一般的な** > **関連付け**] で、[**アーカイブサーバーの関連付け**] チェックボックスをオフにして、[ **OK]** をクリックします。
    
7. 削除するアーカイブサーバーと関連付けられているその他のプール、サーバー、またはデバイスについて、前の手順を繰り返します。
    
8. アーカイブサーバーを右クリックし、[**削除**] をクリックします。
    
9. [**依存**しているストアの削除] で、[ **OK]** をクリックします。
    
10. トポロジを公開し、レプリケーションの状態を確認します。次に、必要に応じて、Skype for Business Server 展開ウィザードを実行します。 
    

