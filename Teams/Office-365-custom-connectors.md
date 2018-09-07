---
title: Microsoft Teams で Office 365 コネクタとカスタム コネクタを使用する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: lucarras
search.appverid: MET150
description: コネクタは、頻繁に使用するサービスからのコンテンツや更新をチャネルに直接配信して、チームを最新の状態に保ちます。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5bb29766d17ea51fdac1e898fdfa6fde72526314
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23867598"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a>Microsoft Teams で Office 365 コネクタとカスタム コネクタを使用する
=======================================================

コネクタは、頻繁に使用するサービスからのコンテンツや更新をチャネルに直接配信して、チームを最新の状態に保ちます。コネクタを使用すると、Microsoft Teams ユーザーは Twitter、Trelloｍ、Wunderlistｍ、GitHub、VSTS などの人気のサービスからの更新情報をチームのチャット ストリームで受け取ることができます。

チームのメンバーは、チームのアクセス許可、およびサービス活動のすべてのチーム メンバーに通知する場合、コネクタを使用した一般的なクラウド サービスをチームを接続できます。 コネクタは、コネクタのままには、セットアップでは最初に、メンバーの後でも機能を引き続きします。 追加と削除] アクセス許可を持つすべてのチーム メンバーには、他のメンバーがコネクタの設定を変更できます。

Office 365 コネクタは、Microsoft Teams と Office 365 グループの両方で使用できます。そのため、すべてのメンバーが同期された状態を容易に保つことができ、関連情報をすばやく受信できます。Microsoft Teams と Exchange は同じコネクタ モデルを使用するため、両方のプラットフォームで同一のコネクタを使用できます。

現時点では、コネクタは Microsoft Teams デスクトップと Web クライアントでのみ追加できます。ただし、コネクタによって投稿された情報はモバイルを含む**すべてのクライアント**で表示できます。

1.  チャネルにコネクタを追加するには、チャネル名の横にある**楕円 (…)** をクリックし、[**コネクタ**] をクリックします。

    ![チャネル名および [コネクタ] オプションが選択された Teams インターフェイスのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2.  ユーザーは利用可能なさまざまなコネクタから選択できます。コネクタを選択して [**追加**] をクリックします。

    ![追加可能なコネクタを示す [コネクタ] ダイアログのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3.  選択したコネクタについて必須情報を入力し、[**保存**] をクリックします。各コネクタは、正常に機能するためにさまざまな必須情報を要求します。一部のコネクタでは、コネクタの構成ページに掲載されるリンクを使用してサービスにサインインする必要があります。

    ![RSS コネクタの [構成] ページのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4.  コネクタによって提供されるデータはチャネルに自動的に投稿されます。

    ![チャネル内の会話を示す Teams インターフェイスのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a>カスタム コネクタを開発する
-----------------------------

基幹業務 (LOB) アプリケーションに統合できるカスタム コネクタを作成することは極めて簡単です。内蔵の**着信 Web フック** コネクタを使用してチャネルのエンドポイントを作成し、HTTP 投稿メソッドを使用して任意のアプリケーションからデータを取得することができます。

1.  **着信 Web フック**をその他のコネクタと同じ方法で追加します。

    ![着信 Web フック コネクタを追加するオプションのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2.  Web フックを作成するには、**名前**を指定し、必要に応じて Web フックの画像を更新します。続けて [**作成**] をクリックします。

    ![着信 Web フック コネクタの [構成] ページのスクリーンショット。 ](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3.  このチャネルにデータをプッシュするアプリケーションは Web フック コネクタの URL を必要とします。**Web フック** を作成したときに、**固有の URL** が作成されます。この URL を開発者と共有して、開発者が必要に応じてアプリケーションによるデータのプッシュを構成できるようにします。

    ![Web フックの固有 URL のスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4.  外部アプリケーションによってコネクタへのデータのプッシュが実行されると、**コネクタ カード** メッセージと呼ばれる特別なメッセージがチャネルの会話リストに表示されます。

    ![コネクタ カード メッセージを示す Teams インターフェイスのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

開発者は、Microsoft Team の Web フック アドレスへの簡潔な JSON ペイロードを含む HTTP 要求を送信することで、このカードを作成するようにアプリケーションを構成することができます。この Web フック アドレスは、ウィザードによって提供される当該エンドポイントの固有 URL です。開発者は、Microsoft Developer Network の「[Getting started with Office 365 Connectors for Microsoft Teams (Microsoft Teams 用の Office 365 コネクタの使用を開始する)](https://go.microsoft.com/fwlink/?linkid=855783)」(英語版) で詳細な手順とコネクタのサンプルを参照できます。その他にも「[Outlook でグループにアプリを接続します](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab)」および「[Office Dev Center – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784)」というリソースが提供されています。
