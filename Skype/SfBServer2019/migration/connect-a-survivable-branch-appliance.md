---
title: 存続可能ブランチ アプライアンスの接続
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: すべての Survivable Branch Appliance (SBA) は、SBA のバックアップレジストラーとして機能するフロントエンドプールと関連付けられています。 フロントエンドプールが Skype for Business Server 2019 に移行された場合、プールがアップグレードされている間、SBA はフロントエンドプールとの関連付けを解除する必要があります。プールが Skype for Business Server 2019 に移行されると、SBA はアップグレードされたフロント E に再関連付けることができます。nd プール。 これには、トポロジビルダーで従来のトポロジから SBA を削除してから、SBA を Skype for Business Server 2019 トポロジに追加する作業が含まれます。 以前の SBA をホームにしているユーザーは、トポロジから SBA を削除する前に、別のフロントエンドプールに移動する必要があります。 SBA が Skype for Business Server 2019 トポロジに追加されると、それらのユーザーを SBA に戻すことができます。 以下に、これらの手順の概要を示します。
ms.openlocfilehash: 7cb933018d24dafb978464338f01f97b25e15539
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275546"
---
# <a name="connect-a-survivable-branch-appliance"></a>存続可能ブランチ アプライアンスの接続

すべての Survivable Branch Appliance (SBA) は、SBA のバックアップレジストラーとして機能するフロントエンドプールと関連付けられています。 フロントエンドプールが Skype for Business Server 2019 に移行されるとき、プールがアップグレードされている間、SBA はフロントエンドプールとの関連付けを解除する必要があります。 プールが Skype for Business Server 2019 に移行された後、SBA は、アップグレードされたフロントエンドプールに再関連付けることができます。 これには、トポロジビルダーで従来のトポロジから SBA を削除してから、SBA を Skype for Business Server 2019 トポロジに追加する作業が含まれます。 以前の SBA をホームにしているユーザーは、トポロジから SBA を削除する前に、別のフロントエンドプールに移動する必要があります。 SBA が Skype for Business Server 2019 トポロジに追加された後は、それらのユーザーを SBA に戻すことができます。 以下に、これらの手順の概要を示します。
  
1. 従来の SBA に所属しているブランチユーザーを別のフロントエンドプールに移動します。
    
2. 既存のフロントエンドプールをバックアップレジストラーとして切断するには、従来のトポロジから SBA を削除します。
    
3. SBA を Skype for Business Server 2019 トポロジに追加し、この新しいフロントエンドプールをバックアップレジストラーとして構成します。 
    
4. ブランチユーザーを新しい Skype for Business Server 2019 SBA に移動します。
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>従来の SBA ブランチサイトをトポロジに追加する

1. **トポロジビルダー**を開きます。
    
2. 左側のウィンドウで、[**ブランチサイト**] を右クリックし、[**新しいブランチサイト**] をクリックします。
    
3. [**新しい分岐サイトの定義**] ダイアログボックスで、[**名前**] をクリックし、ブランチサイトの名前を入力します。
    
4. 省略[**説明**] をクリックし、ブランチサイトにわかりやすい説明を入力します。
    
5. [ **次へ**] をクリックします。
    
6. 省略[次の**新しいブランチサイトの定義**] ダイアログボックスで、次のいずれかの操作を行います。 
    
    1. [**市区町村**] をクリックし、ブランチサイトが配置されている都市の名前を入力します。
    
    2. [**状態/地域**] をクリックして、ブランチサイトが配置されている状態または地域の名前を入力します。
    
    3. [**国コード**] をクリックし、ブランチサイトが配置されている国/地域の2桁の通話コードを入力します。
    
7. [**次へ**] をクリックし、このサイトで Survivable Branch アプライアンスまたはサーバーを使用している場合は、[**このウィザードを閉じるときに、新しい Survivable ウィザードを開く**] チェックボックスを必ずオフにしてください。 [**完了**] をクリックします。
    
8. 従来の SBA を Skype for Business Server 2019 フロントエンドプールに関連付けるには、次の操作を行います。
    
    1. 作成されたブランチサイトを展開します。 
    
    2. [以前のバージョン] を右クリックし、[**新規**] をクリックします。
    
    3. [ **Survivable Branch Appliance**] をクリックします。
    
9. 表示されるウィザードの指示に従います。 ウィザード項目の詳細については、    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Survivable Branch Appliance は、モニタリングストアにのみ関連付けることができます。 
  
10. このサイトで Survivable Branch アプライアンスまたはサーバーを使っていない場合は、[**このウィザードを終了するときに、新しい Survivable ウィザードを開く**] チェックボックスをオフにして、[**完了**] をクリックします。
    
11. トポロジに追加する各ブランチサイトについて、前の手順を繰り返します。
    

