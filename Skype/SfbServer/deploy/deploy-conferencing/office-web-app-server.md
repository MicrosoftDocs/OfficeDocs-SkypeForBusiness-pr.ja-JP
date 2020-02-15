---
title: Skype for Business Server の Office Web Apps サーバーとの統合を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: '概要: このトピックでは、Office Web Apps Server と Skype for Business Server との統合を構成して、web 会議用に PowerPoint プレゼンテーションを有効にする方法について説明します。'
ms.openlocfilehash: fee5939e8441457e3cee66e266baacd144ada288
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983922"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>Skype for Business Server の Office Web Apps サーバーとの統合を構成する
 
**概要:** このトピックでは、Office Web Apps Server と Skype for Business Server との統合を構成して、web 会議用に PowerPoint プレゼンテーションを有効にする方法について説明します。
  
Skype for Business Server は、Office Web Apps サーバーを使用して、web 会議用の PowerPoint プレゼンテーションを処理します。 この方法の利点については、「 [Skype For Business Server で会議を計画](../../plan-your-deployment/conferencing/conferencing.md)する」を参照してください。
  
Office Web Apps サーバーを使用するように Skype for Business Server を構成する前に、Office Web Apps サーバーが既に展開および構成されていることを確認する必要があります。 Office Web Apps サーバーの詳細については、記事「[インフラストラクチャを展開する: Office Online Server](https://go.microsoft.com/fwlink/p/?linkid=257525)」を参照してください。 
  
Office Web Apps サーバーが正常にインストールされ、Web ファームが正しく構成された後、Office Web Apps サーバー検出 URL を Skype for Business に追加して、新しいサーバーと通信するように Skype for Business Server を構成する必要があります。サーバートポロジ。 
  
> [!NOTE]
> Office Web Apps サーバーの最新のイテレーションは、Skype for Business Server でサポートされている Office Online Server と呼ばれています。 詳細については、 [Office Online Server のドキュメント](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx)を参照してください。 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Office Web Apps サーバーと通信するように Skype for Business Server を構成する

Office Web Apps サーバーをトポロジに追加するには、次の手順を実行します。
  
1. Skype for Business Server トポロジビルダーを開きます。
    
2. [**トポロジ ビルダー**] ダイアログ ボックスで、[**既存の展開環境からトポロジをダウンロードする**] をクリックし、[**OK**] をクリックします。
    
3. [**トポロジに名前を付けて保存**] ダイアログ ボックスで、トポロジ ドキュメントの名前 (例: **PreWebAppsServerTopology**) を [**ファイル名**] ボックスに入力し、[**保存**] をクリックします。新しいトポロジで問題が発生した場合、後でこのトポロジを取得して再発行できます。
    
4. トポロジビルダーで、[ **Skype For Business Server**] を展開し、サイトの名前を展開します。次に、[ **Enterprise Edition フロントエンドプール**] を展開して、プールの名前を右クリックし、[**プロパティの編集**] をクリックします。
    
5. [**プロパティの編集**] ダイアログ ボックスの [**全般**] タブで、[**Office Web Apps サーバーの関連付け**] という見出しを探し、[**新規作成**] をクリックします (または、ドロップダウン リストから既存の Office Web Apps サーバーを選択します)。
    
6. [**新しい Office Web Apps サーバーの定義**] ダイアログ ボックスで、Office Web Apps サーバー コンピューターの完全修飾ドメイン名 (FQDN) を [**Office Web Apps サーバーの FQDN**] ボックスに入力します。これを行うと、Office Web Apps サーバー検出の URL が [**Office Web Apps サーバー検出の URL**] ボックスに自動的に入力されます。
    
   - Office Web Apps サーバーがオンプレミスで、Skype for Business Server と同じネットワークゾーンにインストールされている場合、オプションの**Office Web Apps サーバーは外部ネットワーク (境界またはインターネット) に展開**されている必要があります。
    
   - Office Web Apps サーバーを内部ファイアウォールの外側に展開する場合は、[**Office Web Apps サーバーは外部ネットワークで展開 (境界ネットワークまたはインターネット)**] オプションを選択します。
    
7. [**新しい Office Web Apps サーバーの定義**] ダイアログ ボックスで、[**OK**] をクリックし、[**プロパティの編集**] ダイアログ ボックスで [**OK**] をクリックします。 その後、検出 URL がプールの関連付けの1つとして一覧表示されます。
    
Office Web Apps サーバーに関連付ける必要がある各プールに対してこのプロセスを繰り返す必要があります。
  
探索 URL をトポロジに追加した後、更新されたトポロジを公開する必要があります。 これを行うには、トポロジ ビルダーで次の操作を行います。
  
1. [**操作**] をクリックし、[**トポロジの公開**] をクリックします。
    
2. トポロジの公開ウィザードの [**トポロジの公開**] ページで、[**次へ**] をクリックします。
    
3. [**公開ウィザードの完了**] ページで、[**完了**] をクリックします。
    
4. トポロジ ビルダーを閉じます。
    
## <a name="configure-access-for-external-users"></a>外部ユーザーのアクセスを構成する

外部ユーザー (つまり、組織のファイアウォールの外側からログオンしているユーザー) が Office Web Apps サーバーの PowerPoint プレゼンテーションにアクセスできるようにするには、Office Web Apps サーバーとリバースプロキシサーバーを使用する必要があります。 また、web サイト公開ルールを作成して構成する必要があります。これは、ユーザーがサーバーに接続できるようにするために役立ちます。 
  
## <a name="validate-the-configuration"></a>構成を検証する

Office Web Apps サーバーがトポロジに追加され、そのトポロジが公開された後、Skype for Business Server イベントログに2つの新しいイベントログイベントが表示されるはずです。 最初に、LS データ MCU イベント (イベント ID 41034) を追加する必要があります。このイベントは、Office Web Apps サーバーが検出されたことを報告します。
  
 **Web 会議サーバー Office Web Apps サーバーが検出され、PowerPoint コンテンツが有効になっています。**
  
これに加えて、Office Web Apps Server URL を報告する別の LS Data MCU イベント (イベント ID 41032) が表示されます。たとえば、次のように表示されます。
  
 **Web 会議サーバー Office Web Apps サーバーの検出が成功しました。**
  
 **Office Web Apps サーバー内部発表者ページhttps://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp:; embed =**
  
 **Office Web Apps サーバーの内部出席者ページhttps://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp:; embed = true&amp;=**
  
外部ユーザーのアクセスを構成している場合は、次のような内容も表示されます。
  
 **Office Web Apps サーバーの外部発表者https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&ampページ:; embed**
  
 **Office Web Apps サーバーの内部出席者ページ<https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>:;**
  
イベント ID が 41033 の LS Data MCU イベントが表示された場合、Office Web Apps Server の検出が失敗したことを意味します。 その場合、Skype for Business Server は、新しく構成された Office Web Apps サーバーを検出するために必要な回数だけ試行します。 検出プロセスが繰り返し失敗する場合、Office Web Apps Server をトポロジー ドキュメントから削除し、更新されたトポロジーを公開し、接続の問題が解決された後に Office Web Apps Server をトポロジーに再度追加します。
  
Office Web Apps サーバーが正しく構成されており、探索プロセスで認識されている場合は、PowerPoint プレゼンテーションを1組の Skype for Business クライアント間で共有することで、Office Web Apps サーバーが期待どおりに動作していることを確認できます。 ユーザー A が PowerPoint プレゼンテーションを読み込んで表示でき、ユーザー B が会議に参加してそのプレゼンテーションを表示できる場合、Office Web Apps Server は機能しています。
  
Office Web Apps サーバーが正しく構成されているように見えても、PowerPoint プレゼンテーションを共有しようとすると、"サーバー接続の問題により、一部の共有機能は使用できません" というエラーメッセージが表示される可能性があります。 このエラー メッセージを受け取った場合、新しい Office Web Apps Server に関連したフロントエンド サーバー (場合によっては複数) を再起動します。
  

