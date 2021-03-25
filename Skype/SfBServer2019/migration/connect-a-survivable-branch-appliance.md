---
title: 存続可能ブランチ アプライアンスの接続
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
description: すべての存続可能ブランチ アプライアンス (SBA) は、SBA のバックアップ レジストラーとして機能するフロントエンド プールに関連付けられている。 フロントエンド プールを Skype for Business Server 2019 に移行する場合、プールのアップグレード中に SBA をフロントエンド プールから関連付け解除する必要があります。プールが Skype for Business Server 2019 に移行された後、SBA をアップグレードしたフロント エンド プールに再関連付けできます。 これには、トポロジ ビルダーの従来のトポロジから SBA を削除してから、SBA を Skype for Business Server 2019 トポロジに追加する必要があります。 従来の SBA に存在するユーザーは、トポロジから SBA を削除する前に、まず別のフロントエンド プールに移動する必要があります。 SBA を Skype for Business Server 2019 トポロジに追加すると、それらのユーザーは SBA に戻されます。 これらの手順の概要を次に示します。
ms.openlocfilehash: e56bae1631a315b6f42042fb6a7bedd4f144a1b6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113343"
---
# <a name="connect-a-survivable-branch-appliance"></a>存続可能ブランチ アプライアンスの接続

すべての存続可能ブランチ アプライアンス (SBA) は、SBA のバックアップ レジストラーとして機能するフロントエンド プールに関連付けられる。 フロントエンド プールを Skype for Business Server 2019 に移行する場合、プールのアップグレード中に SBA をフロントエンド プールから関連付け解除する必要があります。 プールが Skype for Business Server 2019 に移行された後、SBA をアップグレードされたフロント エンド プールに再関連付けできます。 これには、トポロジ ビルダーの従来のトポロジから SBA を削除してから、SBA を Skype for Business Server 2019 トポロジに追加する必要があります。 従来の SBA に存在するユーザーは、トポロジから SBA を削除する前に、まず別のフロントエンド プールに移動する必要があります。 SBA が Skype for Business Server 2019 トポロジに追加された後、それらのユーザーを SBA に戻す必要があります。 これらの手順の概要を次に示します。
  
1. 従来の SBA のブランチ ユーザーを別のフロント エンド プールに移動します。
    
2. 既存のフロントエンド プールをバックアップ レジストラーとして切断するには、従来のトポロジから SBA を削除します。
    
3. SBA を Skype for Business Server 2019 トポロジに追加し、この新しいフロントエンド プールをバックアップ レジストラーとして構成します。 
    
4. ブランチ ユーザーを新しい Skype for Business Server 2019 SBA に移動します。
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>従来の SBA ブランチ サイトをトポロジに追加する

1. **トポロジ ビルダー** を開きます。
    
2. 左側のウィンドウで、[ブランチ サイト] を右 **クリック** し、[新しいブランチ **サイト] をクリックします**。
    
3. **[新しいブランチ サイトの定義]** ダイアログ ボックスで、**[名前]** をクリックし、ブランチ サイトの名前を入力します。
    
4. (オプション) **[説明]** をクリックし、ブランチ サイトの分かりやすい説明を入力します。
    
5. **[次へ]** をクリックします。
    
6. (オプション) 次の **[新しいブランチ サイトの定義]** ダイアログ ボックスで、以下のいずれかの操作を行います。 
    
    1. **[市区町村]** をクリックし、ブランチ サイトが所在する市区町村の名前を入力します。
    
    2. **[都道府県/地域]** をクリックし、ブランチ サイトが所在する都道府県または地域の名前を入力します。
    
    3. **[国番号]** をクリックし、ブランチ サイトが所在する国または地域の 2 桁番号を入力します。
    
7. [**次へ**] をクリックし、このサイトで存続可能ブランチ アプライアンスまたはサーバーを使用している場合は、[このウィザードが閉じるときに新しい存続可能ウィザードを開く] チェック ボックスをオフにしてください。 **[完了]** をクリックします。
    
8. 従来の SBA を Skype for Business Server 2019 フロントエンド プールに関連付けるには、次の方法を実行します。
    
    1. 作成したブランチ サイトを展開します。 
    
    2. 従来のバージョンを右クリックし、[新規] を **クリックします**。
    
    3. [存続 **可能ブランチ アプライアンス] をクリックします**。
    
9. ウィザードが開くのでその指示に従います。 ウィザードアイテムの詳細については、「    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](/previous-versions/office/lync-server-2013/lync-server-2013-define-a-survivable-branch-appliance-or-server). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > 存続可能ブランチ アプライアンスは、監視ストアにのみ関連付けできます。 
  
10. このサイトで存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーを使用していない場合は、**[このウィザードが閉じたら新しい存続可能ウィザードを開く]** チェック ボックスをオフにして、**[完了]** をクリックします。
    
11. トポロジに追加する各ブランチ サイトに対して、前のステップを繰り返します。
