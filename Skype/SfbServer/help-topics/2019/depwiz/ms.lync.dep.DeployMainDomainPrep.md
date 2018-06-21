---
title: 現在のドメインの準備
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'ビジネス サーバーのユーザーのビジネス サーバーまたは Skype の Skype を実行しているホスト サーバーにドメインを準備するには、手順 5 を完了する必要があります: 準備現在のドメイン、ドメインの準備の実行に使用するセットアップのトピックで説明されているようです。 この手順を完了するには、準備するドメインの Domain Admins グループのメンバー、またはドメインが属するフォレストの Enterprise Admins グループのメンバーとしてログインする必要があります。 ドメインを準備するには、以下の操作を行います。'
ms.openlocfilehash: 7b67521cef97efd2bdfc0da344a8619272899340
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2018
ms.locfileid: "19979891"
---
# <a name="prepare-current-domain"></a>現在のドメインの準備
 
ビジネス サーバーのユーザーのビジネス サーバーまたは Skype の Skype を実行しているホスト サーバーにドメインを準備するのには行う必要があります**手順 5: 現在のドメインを準備する**、[ドメインの準備を実行するセットアップを使用して](http://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx)トピックの説明します。 この手順を完了するには、準備するドメインの Domain Admins グループのメンバー、またはドメインが属するフォレストの Enterprise Admins グループのメンバーとしてログインする必要があります。 ドメインを準備するには、以下の操作を行います。
  
1. ビジネス サーバー 2015 インストール フォルダーまたはメディアの Skype、ビジネス サーバーの展開ウィザードは、Skype を起動するのには、Setup.exe を実行します。
    
2. [**Active Directory の準備**] をクリックして、展開状態が判別されるまで待ちます。
    
3. [**手順 5: 現在のドメインの準備**] で、[**実行**] をクリックします。
    
4. [**コマンドの実行**] ページで [**タスク状態: 完了**] を見つけて、[**ログの表示**] をクリックします。
    
5. [**アクション**] 列で、**ドメインの準備**] を探して、**\<成功\>** ドメインの準備が正常に完了したことを確認して、ログを閉じるし、[**完了**] をクリックする各タスクの最後に実行の結果です。
    
> [!TIP]
> ビジネス サーバーの展開ウィザードは、Skype によって作成されるログ ファイルを確認する必要がある場合、は、展開ウィザードの実行の手順を実行した Active Directory ドメイン サービスのユーザーのユーザー ディレクトリ内のコンピューターでそれらを検索できます。 たとえば、ユーザー Contoso.net のドメインのドメイン管理者としてログインしている場合、ログ ・ ファイル内にある: C:\Users\Administrator.Contoso\AppData\Local\Temp。 
  

