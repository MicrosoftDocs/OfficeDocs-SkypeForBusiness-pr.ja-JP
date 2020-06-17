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
description: すべての存続可能 Branch Appliance (SBA) は、SBA のバックアップレジストラーとして機能するフロントエンドプールに関連付けられています。 フロントエンドプールが Skype for Business Server 2019 に移行される場合、プールがアップグレードされている間はフロントエンドプールと SBA を関連付けないようにする必要があります。プールが Skype for Business Server 2019 に移行されると、SBA をアップグレードしたフロントエンドプールに再関連付けすることができます。 これには、トポロジビルダーの従来のトポロジから SBA を削除してから、SBA を Skype for Business Server 2019 トポロジに追加する必要があります。 SBA をトポロジから削除する前に、従来の SBA に所属するユーザーを別のフロントエンドプールに移動する必要があります。 SBA が Skype for Business Server 2019 トポロジに追加されると、それらのユーザーは SBA に戻ることができます。 これらの手順の概要を次に示します。
ms.openlocfilehash: 23fea7694a754b82ecad684d2ea02b603a6c7299
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751549"
---
# <a name="connect-a-survivable-branch-appliance"></a>存続可能ブランチ アプライアンスの接続

すべての存続可能 Branch Appliance (SBA) は、SBA のバックアップレジストラーとして機能するフロントエンドプールに関連付けられています。 フロントエンドプールが Skype for Business Server 2019 に移行される場合、プールがアップグレードされている間は、フロントエンドプールとの関連付けを解除する必要があります SBA。 プールが Skype for Business Server 2019 に移行された後、SBA をアップグレードしたフロントエンドプールに再関連付けすることができます。 これには、トポロジビルダーの従来のトポロジから SBA を削除してから、SBA を Skype for Business Server 2019 トポロジに追加する必要があります。 SBA をトポロジから削除する前に、従来の SBA に所属するユーザーを別のフロントエンドプールに移動する必要があります。 SBA が Skype for Business Server 2019 トポロジに追加された後、それらのユーザーを SBA に戻すことができます。 これらの手順の概要を次に示します。
  
1. 従来の SBA に所属するブランチユーザーを別のフロントエンドプールに移動します。
    
2. 既存のフロントエンドプールをバックアップレジストラーとして切断するには、SBA を従来のトポロジから削除します。
    
3. SBA を Skype for Business Server 2019 トポロジに追加し、この新しいフロントエンドプールをバックアップレジストラーとして構成します。 
    
4. ブランチユーザーを新しい Skype for Business Server 2019 SBA に移動します。
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>従来の SBA ブランチサイトをトポロジに追加する

1. **トポロジ ビルダー**を開きます。
    
2. 左側のウィンドウで、[**ブランチサイト**] を右クリックし、[**新しいブランチサイト**] をクリックします。
    
3. **[新しいブランチ サイトの定義]** ダイアログ ボックスで、**[名前]** をクリックし、ブランチ サイトの名前を入力します。
    
4. (オプション) **[説明]** をクリックし、ブランチ サイトの分かりやすい説明を入力します。
    
5. **[次へ]** をクリックします。
    
6. (オプション) 次の **[新しいブランチ サイトの定義]** ダイアログ ボックスで、以下のいずれかの操作を行います。 
    
    1. **[市区町村]** をクリックし、ブランチ サイトが所在する市区町村の名前を入力します。
    
    2. **[都道府県/地域]** をクリックし、ブランチ サイトが所在する都道府県または地域の名前を入力します。
    
    3. **[国番号]** をクリックし、ブランチ サイトが所在する国または地域の 2 桁番号を入力します。
    
7. [**次へ**] をクリックし、このサイトで存続可能ブランチアプライアンスまたはサーバーを使用している場合は、必ず [**このウィザードを閉じるときに新しい存続可能ウィザードを開く**] チェックボックスをオフにします。 [**完了**] をクリックします。
    
8. 従来の SBA を Skype for Business Server 2019 のフロントエンドプールに関連付けるには、次のようにします。
    
    1. 作成したブランチ サイトを展開します。 
    
    2. [レガシバージョン] を右クリックし、[**新規作成**] をクリックします。
    
    3. [**存続可能 Branch Appliance**] をクリックします。
    
9. ウィザードが開くのでその指示に従います。 ウィザードアイテムの詳細については、    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > 存続可能ブランチアプライアンスは、監視ストアにのみ関連付けることができます。 
  
10. このサイトで存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーを使用していない場合は、**[このウィザードが閉じたら新しい存続可能ウィザードを開く]** チェック ボックスをオフにして、**[完了]** をクリックします。
    
11. トポロジに追加する各ブランチ サイトに対して、前のステップを繰り返します。
    

