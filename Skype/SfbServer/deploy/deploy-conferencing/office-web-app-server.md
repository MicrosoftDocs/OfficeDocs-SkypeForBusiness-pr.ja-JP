---
title: Skype for Business Server の Office Web Apps サーバーとの統合を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: '概要: このトピックでは、Office Web Apps サーバーと Skype for Business Server の統合を構成し、Web 会議用の PowerPoint プレゼンテーションを有効にする方法について説明します。'
ms.openlocfilehash: 99b0ab34af655b95fab3d92973f948d30e3e51f8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233915"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>Skype for Business Server の Office Web Apps サーバーとの統合を構成する
 
**概要:** このトピックでは、Office Web Apps サーバーと Skype for Business Server の統合を構成して、Web 会議用の PowerPoint プレゼンテーションを有効にする方法について説明します。
  
Skype for Business Server は Office Web Apps サーバーを使用して、web 会議用の PowerPoint プレゼンテーションを処理します。 この方法の利点については、「 [Skype For Business Server の会議の計画](../../plan-your-deployment/conferencing/conferencing.md)」を参照してください。
  
Skype for Business Server で Office Web Apps サーバーを使用するように構成するには、Office Web Apps サーバーが既に展開され、構成されていることを確認する必要があります。 Office Web Apps サーバーについては、「[インフラストラクチャを展開する: Office Online server](https://go.microsoft.com/fwlink/p/?linkid=257525)」の記事を参照してください。 
  
Office Web Apps サーバーが正常にインストールされ、Web ファームが正常に構成されたら、Office Web Apps Server discovery URL を Skype for Business に追加して、新しいサーバーと通信するように Skype for Business Server を構成する必要があります。サーバートポロジ。 
  
> [!NOTE]
> Office Web Apps サーバーの最新のイテレーションは、Skype for Business Server でサポートされている Office Online Server という名前です。 詳細については、「 [Office Online Server のドキュメント](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx)」を参照してください。 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Office Web Apps サーバーと通信できるように Skype for Business Server を構成する

トポロジに Office Web Apps サーバーを追加するには、次の手順を行います。
  
1. Skype for Business Server トポロジビルダーを開きます。
    
2. [**トポロジ ビルダー**] ダイアログ ボックスで、[**既存の展開からトポロジをダウンロードする**] を選択して [**OK**] をクリックします。
    
3. [**トポロジに名前を付けて保存**] ダイアログ ボックスで、トポロジ ドキュメントの名前 (例: **PreWebAppsServerTopology**) を [**ファイル名**] ボックスに入力し、[**保存**] をクリックします。新しいトポロジで問題が発生した場合、後でこのトポロジを取得して再発行できます。
    
4. トポロジ ビルダーで、[**Skype for Business Server**]、ユーザーのサイトの名前、[**Enterprise Edition フロントエンド プール**] の順に展開します。いずれかのプールの名前を右クリックし、[**プロパティの編集**] をクリックします。
    
5. [**プロパティの編集**] ダイアログ ボックスの [**全般**] タブで、[**Office Web Apps サーバーの関連付け**] という見出しを探し、[**新規作成**] をクリックします (または、ドロップダウン リストから既存の Office Web Apps サーバーを選択します)。
    
6. [**新しい Office Web Apps サーバーの定義**] ダイアログ ボックスで、Office Web Apps サーバー コンピューターの完全修飾ドメイン名 (FQDN) を [**Office Web Apps サーバーの FQDN**] ボックスに入力します。これを行うと、Office Web Apps サーバー検出の URL が [**Office Web Apps サーバー検出の URL**] ボックスに自動的に入力されます。
    
   - Office Web Apps サーバーがオンプレミスでインストールされていて、Skype for Business Server と同じネットワークゾーンにインストールされている場合は、 **Office Web Apps サーバーは外部ネットワーク ([境界/インターネット]) に展開**されます。
    
   - Office Web Apps サーバーを内部ファイアウォールの外側に展開する場合は、[**Office Web Apps サーバーは外部ネットワークで展開 (境界ネットワークまたはインターネット)**] オプションをオンにします。
    
7. [**新しい Office Web Apps サーバーの定義**] ダイアログ ボックスで、[**OK**] をクリックし、[**プロパティの編集**] ダイアログ ボックスで [**OK**] をクリックします。 検出 URL がプールの関連付けの1つとして表示されます。
    
Office Web Apps サーバーに関連付ける必要がある各プールに対してこのプロセスを繰り返す必要があります。
  
検出 URL をトポロジに追加した後、更新されたトポロジを公開する必要があります。これを行うには、トポロジ ビルダーで次の操作を行います。
  
1. [**操作**] をクリックし、[**トポロジの公開**] をクリックします。
    
2. トポロジの公開ウィザードの [**トポロジの公開**] ページで、[**次へ**] をクリックします。
    
3. [**公開ウィザードの完了**] ページで、[**完了**] をクリックします。
    
4. トポロジ ビルダーを閉じます。
    
## <a name="configure-access-for-external-users"></a>外部ユーザー用のアクセスの構成

外部ユーザー (つまり、組織のファイアウォール外からログオンしているユーザー) が Office Web Apps Server PowerPoint プレゼンテーションにアクセスできるようにするには、Office Web Apps サーバーとリバースプロキシサーバーを使用する必要があります。 また、web サイトの公開ルールを作成して構成する必要があります。これは、ユーザーがサーバーに接続できるようにするために役立ちます。 
  
## <a name="validate-the-configuration"></a>構成を検証する

Office Web Apps サーバーをトポロジに追加した後で、そのトポロジが公開されると、Skype for Business Server イベントログに2つの新しいイベントログイベントが表示されます。 最初に、LS データ MCU イベント (イベント ID 41034) を追加する必要があります。このイベントは、Office Web Apps サーバーが検出されたことを報告します。
  
 **Web 会議サーバー Office Web Apps サーバーが検出され、PowerPoint コンテンツが有効になりました。**
  
これに加えて、Office Web Apps Server URL を報告する別の LS Data MCU イベント (イベント ID 41032) が表示されます。たとえば、次のように表示されます。
  
 **Web 会議サーバー Office Web Apps サーバー検出が成功しました。**
  
 **Office Web Apps サーバーの内部発表者https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&ampページ:; 埋め込み =**
  
 **Office Web Apps サーバーの内部出席者ページhttps://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp:; 埋め込み = true&amp;=**
  
外部ユーザーへのアクセスを構成している場合は、次のような内容も表示されます。
  
 **Office Web Apps サーバーの外部発表者https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&ampページ:; 埋め込み**
  
 **Office Web Apps サーバーの内部出席者ページ<https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>:;**
  
Office Web Apps サーバーの検出に失敗したことを示す、イベント ID が41033の LS データ MCU イベントが表示される場合。 この場合、Skype for Business Server は、新しく構成された Office Web Apps サーバーを検出するために必要な回数だけ試します。 検出プロセスが繰り返し失敗する場合は、トポロジドキュメントから Office Web Apps サーバーを削除し、更新されたトポロジを公開して、接続の問題が解決した後で、Office Web Apps サーバーをトポロジに追加してみます。
  
Office Web Apps サーバーが正しく構成されていて、検出プロセスによって認識されている場合、Office Web Apps サーバーが正常に動作していることを確認するには、1組の Skype for Business クライアント間で PowerPoint プレゼンテーションを共有します。 ユーザー A が PowerPoint プレゼンテーションを読み込み、表示できる場合に、ユーザー B が会議に参加すると、そのプレゼンテーションが Office Web Apps サーバーで動作することを確認できます。
  
Office Web Apps サーバーが正しく構成されているように見えても、PowerPoint プレゼンテーションを共有しようとすると、"サーバーの接続に問題が発生したため、一部の共有機能を利用できません" というエラーメッセージが表示されることがあります。 このエラーメッセージが表示された場合は、新しい Office Web Apps サーバーに関連付けられたフロントエンドサーバー (またはサーバー) を再起動する必要があります。
  

