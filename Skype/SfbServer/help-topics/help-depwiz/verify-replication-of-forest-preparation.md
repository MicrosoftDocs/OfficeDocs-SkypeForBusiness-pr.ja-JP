---
title: フォレストの準備のレプリケーションを確認します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: グローバル カタログのレプリケーションとフォレストの準備時にオブジェクトの作成であることを確認するのには成功して、次の操作を行います。
ms.openlocfilehash: cfb993a9a80bf4b37e76712a58aa6c1fb0c270c3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="verify-replication-of-forest-preparation"></a>フォレストの準備のレプリケーションを確認します。
 
グローバル カタログのレプリケーションとフォレストの準備時にオブジェクトの作成であることを確認するのには成功して、次の操作を行います。
  
1. フォレストの準備を実行したフォレスト内のドメイン コントローラー (他のドメイン コントローラーからリモート サイトにあるドメイン コントローラーを推奨) で、[**Active Directory ユーザーとコンピューター**] を開きます。
    
2. [**Active Directory ユーザーとコンピューター**] で、フォレストまたは子ドメインのドメイン名を展開します。
    
3. 左側のウィンドウで [ **Users** ] コンテナーをクリックし、右側のペインでのユニバーサル グループ CsAdministrator を探します。 CsAdministrator (8 つの他の新しいユニバーサル ・ グループ間で Cs で始まる) が存在する場合は、フォレストの準備のレプリケーションが成功しています。
    
4. グループがまだ存在しない場合は、レプリケーションを強制的にまたは 15 分間待機して右側のウィンドウを更新できます。 グループが表示されている場合、レプリケーションは完了しています。
    
> [!TIP]
> ビジネス サーバーの展開ウィザードは、Skype によって作成されるログ ファイルを確認するには場合、は、展開ウィザードが実行しているコンピューターの手順を実行した Active Directory ドメイン サービスのユーザーのユーザー ディレクトリ内にそれらを検索できます。 たとえば、ユーザー Contoso.net のドメインのドメイン管理者としてログインしている場合、ログ ・ ファイル内にある: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

