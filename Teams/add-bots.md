---
title: "Microsoft のチームで非公開チャットとチャネルのコンポーネントを追加します。"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Microsoft チームで非公開チャットとチャネルのコンポーネントを追加する方法について、ユーザー設定のコンポーネントを作成する、側では、独自の結果を読み込む秘密チャットします。"
ms.openlocfilehash: c7f2aec398728f310fab780e96d4df09e4b7f582
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="add-bots-for-private-chats-and-channels-in-microsoft-teams"></a>Microsoft のチームで非公開チャットとチャネルのコンポーネントを追加します。
==========================================================

コンポーネントをクエリに応答するか、他の更新プログラムが自動に通知を受け取るか興味を持ったユーザーの詳細についての通知。コンポーネントには、操作するタスクの管理、スケジュール、および Microsoft チームでチャットを行うを通じて、ポーリングなどのクラウド サービスにユーザーができるようにします。Microsoft チーム ロボットでは、 [Microsoft 結果 Framework](https://go.microsoft.com/fwlink/?linkid=854370)構築されます。チームが Microsoft には、このフレームワークを使用して開発されたコンポーネントが簡単に有効にすることができます。詳細については、 [Office 365 の組織で Microsoft チームを有効にする機能](enable-features-office-365.md)を参照してください。

現時点では、Microsoft チームは、プライベート チャット チーム内でのチャンネルでコンポーネントをサポートします。管理者は、コンポーネントの使用を許可または Office 365 のテナント内の禁止かどうかを制御できます。<span id="_T-Bot" class="anchor"></span>

コミュニティが開発したコンポーネントは、Microsoft チーム内で利用できます。ユーザー設定のコンポーネントが機能するは、テナント レベルでは、結果の機能と結果のサイドの読み込みを有効にする必要があります。プライベート チャットまたはチャンネルのコンポーネントを使用できます。チャンネルのチームの所有者またはメンバーは、コンポーネントを追加できます。

詳細については、[アプリとサービス](https://support.office.com/en-us/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)の「を使用するロボット」を参照してください。 








 

<a name="create-custom-bots-for-microsoft-teams"></a>Microsoft チームのユーザー設定のコンポーネントを作成します。
--------------------------------------

簡単に作成できますに統合する結果 LOB アプリケーションに Microsoft 結果フレームワークを使用します。開発し、独自のコンポーネントを発行する方法については[、結果をチームが Microsoft のテストの作成と](https://go.microsoft.com/fwlink/?linkid=854371)ガイダンスを参照してください。

結果を作成して結果フレームワークに登録すると、それを公開することもできます。公開しない場合、結果はプライベートは残ります。ユーザーが、結果を使用する前にログインを要求することもできます。必要なログインでは、結果のアプリケーションの ID がわかっている場合でも、組織の従業員のみが、結果にアクセスできることを確認します。コンポーネントを使用して、Active Directory に対してユーザーを認証する方法については、GitHub [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372)を参照してください。

コンポーネントをテストするには、チームに展開する前に、[結果 Framework エミュレーター](https://go.microsoft.com/fwlink/?linkid=854373)を使用します。

<a name="side-load-your-own-bot-for-private-chat"></a>サイド プライベート通話用の独自の結果を読み込む
---------------------------------------

1.  結果を作成した後は、開発すると、結果の**結果のダッシュ ボード**[ページ](https://go.microsoft.com/fwlink/?linkid=854374)に移動し、[の**詳細について**は、[ **Microsoft アプリケーションの ID**をコピーします。![が強調表示された Microsoft アプリケーション id を結果の詳細] ページのスクリーン ショット。](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png) 



2.  Microsoft チーム内で**[チャット**] ウィンドウで、[**チャットの追加] アイコン**を選択します。用**に**結果の**Microsoft アプリ ID**を貼り付けます。![追加チャットのアイコンで、[チャット] ウィンドウと Microsoft アプリ id が強調表示されている行のスクリーン ショット。](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)



3.  アプリ ID**結果名**に解決され、その結果に、会話を行うことができます。
