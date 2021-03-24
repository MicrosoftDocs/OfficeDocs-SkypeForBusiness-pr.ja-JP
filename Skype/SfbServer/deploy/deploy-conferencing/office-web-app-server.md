---
title: Skype for Business Server Office Web Apps サーバーとの統合を構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: '概要: Web Apps Server と Skype for Business Server の間の統合を構成して、Web 会議Office PowerPoint プレゼンテーションを有効にする方法については、このトピックを参照してください。'
ms.openlocfilehash: 24332154efacd0dac889bcad5b95379b28faf7a2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103653"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>Skype for Business Server Office Web Apps サーバーとの統合を構成する
 
**概要:** このトピックでは、Web Apps Server と Skype for Business Server Officeの統合を構成して、Web 会議用の PowerPoint プレゼンテーションを有効にする方法について説明します。
  
Skype for Business Server は、Web Office会議用の PowerPoint プレゼンテーションを処理する Web Apps サーバーを採用しています。 この方法の利点については、「Skype for Business Server での会議の計画 [」を参照してください](../../plan-your-deployment/conferencing/conferencing.md)。
  
Skype for Business Server で Web Apps サーバー Office構成する前に、Web Apps サーバー Office展開および構成されていることを確認する必要があります。 Web Apps Server のOfficeについては、「Deploy the [infrastructure: Office」を参照してください](/webappsserver/deploy-the-infrastructure-office-web-apps-server)。 
  
Office Web Apps サーバーが正常にインストールされ、Web ファームが正しく構成された後、Office Web Apps Server 検出 URL を Skype for Business Server トポロジに追加して、新しいサーバーと通信するように Skype for Business Server を構成する必要があります。 
  
> [!NOTE]
> Web Apps Server の最新Officeは、Skype for Business Server でOfficeオンライン サーバーという名前です。 詳細については、オンライン サーバーのドキュメント [Office参照してください](/officeonlineserver/office-online-server)。 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Skype for Business Server が Web Apps サーバーと通信Office構成する

Web Apps server Officeトポロジに追加するには、次の手順を実行します。
  
1. Skype for Business Server トポロジ ビルダーを開きます。
    
2. [**トポロジ ビルダー**] ダイアログ ボックスで、[**既存の展開環境からトポロジをダウンロードする**] をクリックし、[**OK**] をクリックします。
    
3. [**トポロジに名前を付けて保存**] ダイアログ ボックスで、トポロジ ドキュメントの名前 (例: **PreWebAppsServerTopology**) を [**ファイル名**] ボックスに入力し、[**保存**] をクリックします。新しいトポロジで問題が発生した場合、後でこのトポロジを取得して再発行できます。
    
4. トポロジ ビルダーで **、[Skype for Business Server]** を展開し、サイトの名前を展開し **、[Enterprise Edition** フロントエンド プール] を展開し、プールの 1 つの名前を右クリックし、[プロパティの編集] をクリック **します**。
    
5. [**プロパティの編集**] ダイアログ ボックスの [**全般**] タブで、[**Office Web Apps サーバーの関連付け**] という見出しを探し、[**新規作成**] をクリックします (または、ドロップダウン リストから既存の Office Web Apps サーバーを選択します)。
    
6. [**新しい Office Web Apps サーバーの定義**] ダイアログ ボックスで、Office Web Apps サーバー コンピューターの完全修飾ドメイン名 (FQDN) を [**Office Web Apps サーバーの FQDN**] ボックスに入力します。これを行うと、Office Web Apps サーバー検出の URL が [**Office Web Apps サーバー検出の URL**] ボックスに自動的に入力されます。
    
   - Office Web Apps サーバーがオンプレミスで Skype for Business Server と同じネットワーク 領域にインストールされている場合は、オプション **Office Web Apps Server** が外部ネットワーク (境界/インターネット) に展開される必要があります。
    
   - Office Web Apps サーバーを内部ファイアウォールの外側に展開する場合は、[**Office Web Apps サーバーは外部ネットワークで展開 (境界ネットワークまたはインターネット)**] オプションを選択します。
    
7. [**新しい Office Web Apps サーバーの定義**] ダイアログ ボックスで、[**OK**] をクリックし、[**プロパティの編集**] ダイアログ ボックスで [**OK**] をクリックします。 検出 URL は、プールの関連付けの 1 つとして一覧表示されます。
    
Office Web Apps サーバーに関連付ける必要がある各プールに対してこのプロセスを繰り返す必要があります。
  
探索 URL をトポロジに追加したら、更新されたトポロジを公開する必要があります。 これを行うには、トポロジ ビルダーで次の操作を行います。
  
1. [**操作**] をクリックし、[**トポロジの公開**] をクリックします。
    
2. トポロジの公開ウィザードの [**トポロジの公開**] ページで、[**次へ**] をクリックします。
    
3. [**公開ウィザードの完了**] ページで、[**完了**] をクリックします。
    
4. トポロジ ビルダーを閉じます。
    
## <a name="configure-access-for-external-users"></a>外部ユーザーのアクセスを構成する

外部ユーザー (つまり、組織のファイアウォールの外部からログオンしているユーザー) に Office Web Apps Server PowerPoint プレゼンテーションへのアクセスを許可する場合は、Office Web Apps Server とリバース プロキシ サーバーを使用する必要があります。 また、ユーザーがサーバーに接続できる Web サイト発行ルールを作成して構成する必要があります。 
  
## <a name="validate-the-configuration"></a>構成の検証

Web Officeサーバーがトポロジに追加され、そのトポロジが公開された後、Skype for Business Server イベント ログに 2 つの新しいイベント ログ イベントが表示されます。 まず、LS データ MCU イベント (イベント ID 41034) を追加する必要があります。このイベントは、Web Apps サーバー Officeが検出されたと報告します。
  
 **Web Apps サーバー Office Web 会議サーバーが検出された場合、PowerPoint コンテンツが有効になります。**
  
これに加えて、Office Web Apps Server URL を報告する別の LS Data MCU イベント (イベント ID 41032) が表示されます。たとえば、次のように表示されます。
  
 **Web Apps サーバー Office Web 会議サーバーの検出が成功しました。**
  
 **Office Web Apps Server の内部発表者ページ: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ;embed=**
  
 **Office Web Apps Server の内部出席者ページ: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp ;embed=true&amp;=**
  
外部ユーザーのアクセスを構成している場合は、次のような情報も表示されます。
  
 **Office Web Apps Server 外部発表者ページ: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ;embed**
  
 **Office Web Apps Server の内部出席者 <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp> ページ:**
  
イベント ID が 41033 の LS Data MCU イベントが表示された場合、Office Web Apps Server の検出が失敗したことを意味します。 その場合、Skype for Business Server は、新しく構成された Web Apps サーバーを検出するために必要な回数Office試します。 検出プロセスが繰り返し失敗する場合、Office Web Apps Server をトポロジー ドキュメントから削除し、更新されたトポロジーを公開し、接続の問題が解決された後に Office Web Apps Server をトポロジーに再度追加します。
  
Office Web Apps サーバーが正しく構成されている場合、検出プロセスによって認識されている場合は、2 つの Skype for Business クライアント間で PowerPoint プレゼンテーションを共有することで、Office Web Apps Server が期待通り動作しているのを確認できます。 ユーザー A が PowerPoint プレゼンテーションを読み込んで表示でき、ユーザー B が会議に参加してそのプレゼンテーションを表示できる場合、Office Web Apps Server は機能しています。
  
Web Apps サーバー Office正しく構成されている場合でも、PowerPoint プレゼンテーションを共有しようとするときに、「サーバー接続の問題により一部の共有機能が利用できない」というエラー メッセージが表示される可能性があります。 このエラー メッセージを受け取った場合、新しい Office Web Apps Server に関連したフロントエンド サーバー (場合によっては複数) を再起動します。
