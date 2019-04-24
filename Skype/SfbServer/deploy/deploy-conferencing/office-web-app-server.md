---
title: ビジネス サーバー用の Skype では、Office Web アプリケーション サーバーとの統合を構成します。
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: '概要: は、PowerPoint のプレゼンテーションを web 会議を有効にするには、Office Web アプリケーション サーバーと Skype ビジネス サーバーの間の統合を構成する方法については、このトピックを読みます。'
ms.openlocfilehash: 69cdbd50387f2e3267a0fc2acb38e47260970578
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223825"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>ビジネス サーバー用の Skype では、Office Web アプリケーション サーバーとの統合を構成します。
 
**の概要:** Office Web アプリケーション サーバーと web 会議のための PowerPoint プレゼンテーションを有効にする Skype ビジネス サーバーの間の統合を構成する方法については、このトピックを参照してください。
  
Skype ビジネス サーバー用には、web 会議のための PowerPoint プレゼンテーションを処理するために Office の Web アプリケーション サーバーが使用されています。 このアプローチの利点の詳細については、[ビジネスのサーバー用の Skype での会議の計画](../../plan-your-deployment/conferencing/conferencing.md)を参照してください。
  
ビジネス サーバーは、Office Web アプリケーション サーバーを使用するの Skype を構成することができます、前に、Office Web アプリケーション サーバーが既に展開され、構成されていることを確認する必要があります。 Office Web アプリケーション サーバーについては、資料を参照してください[インフラストラクチャを展開します。 Office オンラインのサーバー](https://go.microsoft.com/fwlink/p/?linkid=257525)。 
  
Office Web アプリケーション サーバーが正常にインストールされて正しく構成されている Web ファーム、行う必要がありますし、Skype、Skype をビジネスのために Office の Web アプリケーション サーバーの検出 URL を追加することによって新しいサーバーと通信するためにビジネスのサーバーの後サーバー トポロジです。 
  
> [!NOTE]
> Office オンライン サーバー、ビジネス サーバーの Skype がサポートしている Office Web アプリケーション サーバーの最新のイテレーションの名前です。 詳細については、 [Office オンラインのサーバーのマニュアル](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx)を参照してください。 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Office Web アプリケーション サーバーと通信するサーバーをビジネス用の Skype を構成します。

トポロジに Office Web Apps サーバーを追加するには、次の手順を行います。
  
1. Skype をビジネス サーバー トポロジ ビルダーを開きます。
    
2. [**トポロジ ビルダー**] ダイアログ ボックスで、[**既存の展開からトポロジをダウンロードする**] を選択して [**OK**] をクリックします。
    
3. [**トポロジに名前を付けて保存**] ダイアログ ボックスで、トポロジ ドキュメントの名前 (例: **PreWebAppsServerTopology**) を [**ファイル名**] ボックスに入力し、[**保存**] をクリックします。新しいトポロジで問題が発生した場合、後でこのトポロジを取得して再発行できます。
    
4. トポロジ ビルダーで、[**Skype for Business Server**]、ユーザーのサイトの名前、[**Enterprise Edition フロントエンド プール**] の順に展開します。いずれかのプールの名前を右クリックし、[**プロパティの編集**] をクリックします。
    
5. [**プロパティの編集**] ダイアログ ボックスの [**全般**] タブで、[**Office Web Apps サーバーの関連付け**] という見出しを探し、[**新規作成**] をクリックします (または、ドロップダウン リストから既存の Office Web Apps サーバーを選択します)。
    
6. [**新しい Office Web Apps サーバーの定義**] ダイアログ ボックスで、Office Web Apps サーバー コンピューターの完全修飾ドメイン名 (FQDN) を [**Office Web Apps サーバーの FQDN**] ボックスに入力します。これを行うと、Office Web Apps サーバー検出の URL が [**Office Web Apps サーバー検出の URL**] ボックスに自動的に入力されます。
    
   - Office Web アプリケーション サーバーがインストールされている設置型の場合と、ネットワークと同じゾーンのビジネス サーバー オプションでは、Skype で**Office Web アプリケーション サーバーが外部ネットワーク (つまり、境界領域またはインターネット) に配置**する必要がありますオフにします。
    
   - Office Web Apps サーバーを内部ファイアウォールの外側に展開する場合は、[**Office Web Apps サーバーは外部ネットワークで展開 (境界ネットワークまたはインターネット)**] オプションをオンにします。
    
7. [**新しい Office Web Apps サーバーの定義**] ダイアログ ボックスで、[**OK**] をクリックし、[**プロパティの編集**] ダイアログ ボックスで [**OK**] をクリックします。Office Online の検出 URL がプールの関連付けの 1 つとして表示されます。
    
Office Web Apps サーバーに関連付ける必要がある各プールに対してこのプロセスを繰り返す必要があります。
  
検出 URL をトポロジに追加した後、更新されたトポロジを公開する必要があります。これを行うには、トポロジ ビルダーで次の操作を行います。
  
1. [**操作**] をクリックし、[**トポロジの公開**] をクリックします。
    
2. トポロジの公開ウィザードの [**トポロジの公開**] ページで、[**次へ**] をクリックします。
    
3. [**公開ウィザードの完了**] ページで、[**完了**] をクリックします。
    
4. トポロジ ビルダーを閉じます。
    
## <a name="configure-access-for-external-users"></a>外部ユーザー用のアクセスの構成

外部ユーザー (組織のファイアウォールの外側からログオンしているユーザー) をする場合、Office Web アプリケーション サーバーの PowerPoint プレゼンテーションにアクセスし、Office Web アプリケーション サーバーとリバース プロキシ サーバーを使用する必要がありますが。 作成し、ユーザーがサーバーに接続することであることを確認に役立ちますが、web サイト公開ルールを構成する必要があります。 
  
## <a name="validate-the-configuration"></a>構成を検証する

Office Web アプリケーション サーバー、トポロジに追加した後、そのトポロジが公開された後、Skype のビジネス サーバーのイベント ログに新しいイベント ログのイベントを 2 つを参照してくださいする必要があります。 最初に、データ MCU の LS イベント (イベント ID 41034) を追加する必要があります。このイベントは、Office Web アプリケーション サーバーが検出されたことが報告されます。
  
 **Web 会議サーバー Office Web Apps サーバーが検出され、PowerPoint コンテンツが有効になりました。**
  
これに加えて、Office Web Apps Server URL を報告する別の LS Data MCU イベント (イベント ID 41032) が表示されます。たとえば、次のように表示されます。
  
 **Web 会議サーバー Office Web Apps サーバー検出が成功しました。**
  
 **Office Web アプリケーション サーバー内部の発表者のページ: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp; 埋め込む =**
  
 **Office Web アプリケーション サーバー内部の出席者のページ: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp; 埋め込む = true&amp;=**
  
外部ユーザーのアクセスを構成した場合、以下のようにも表示されます。
  
 **Office Web アプリケーション サーバーの外部発表のページ: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp; を埋め込む**
  
 **Office Web アプリケーション サーバー内部の出席者のページ:<https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>です。**
  
表示する場合は、Office Web アプリケーション サーバーの検出のことを意味する 41033 のイベント ID を持つデータ MCU の LS イベントに失敗しました。 Skype ビジネス サーバーの場合は、新たに構成されている Office の Web アプリケーション サーバーを検出するために必要な回数だけ再試行されます。 検出プロセスが繰り返し失敗した場合、トポロジ ドキュメントから Office Web アプリケーション サーバーを削除、更新されたトポロジを公開する、接続の問題が解決された後に、トポロジに Office Web アプリケーション サーバーを追加してくださいしてください。
  
Office Web アプリケーション サーバーを正しく構成するが表示され、検出プロセスによって認識された場合は、Skype のビジネス クライアント用のペアの間で PowerPoint プレゼンテーションを共有することで期待どおりに、Office Web アプリケーション サーバーが動作しているを確認できます。 ユーザー A は、ロードし、PowerPoint プレゼンテーションを表示し、ユーザー B が会議に参加し、そのプレゼンテーションを参照してください場合は、Office Web アプリケーション サーバーが動作してください。
  
正しく構成するのには、Office Web アプリケーション サーバーが表示されたら、たとえ可能性があります可能性があります、エラー メッセージが表示「いくつかの共有機能はサーバー接続の問題のために利用可能な」しようとすると、PowerPoint のプレゼンテーションを共有します。 そのエラー メッセージが表示される場合は、新しいオフィスの Web アプリケーション サーバーに関連付けられているフロント エンド サーバー (またはサーバー) を再起動する必要があります。
  

