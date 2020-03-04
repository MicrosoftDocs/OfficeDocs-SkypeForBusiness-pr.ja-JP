---
title: Microsoft Teams を使用してリモート ワーカーをサポートする
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: dansteve
localization_priority: Priority
search.appverid: MET150
description: このガイダンスは、Microsoft Teams を使用して組織のリモート ワーカーの生産性を向上させるために使用できます。特に、新型コロナウイルス感染症 (COVID-19) 発生への対策として従業員が在宅勤務 (WFH) となった場合に役立ちます。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80af76906697ef2510fe75d8764e8908cdbbd976
ms.sourcegitcommit: ed0ecb3b1250a23d3b91a5a33256aee1c3119db1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2020
ms.locfileid: "42374314"
---
# <a name="support-remote-workers-using-microsoft-teams"></a>Microsoft Teams を使用してリモート ワーカーをサポートする

この記事に記載されているベスト プラクティスを使用して、リモートまたは自宅で作業を行うユーザーをサポートしてください。

## <a name="technical"></a>技術面に関する説明

1.  [すべてのユーザーに対して Teams が有効になっている](assign-teams-licenses.md)ことを確認します
    
      - [Teams E1 試用版](e1-trial-license.md)、[Teams Exploratory](teams-exploratory.md)、または[無料版の Teams](https://support.office.com/article/Welcome-to-Microsoft-Teams-free-6d79a648-6913-4696-9237-ed13de64ae3c) に関する説明を確認し、社員全員が Teams を利用できるようにします。

      - リモートの従業員は、会議や電話会議に大きく依存しています。 これらのワークロードをまだ展開していない場合は、「[Teams でのミーティングと会議](deploy-meetings-microsoft-teams-landing-page.md)」を参照してください。

2.  Teams についてユーザーに通知します。 [Teams カスタマー サクセス キット](https://download.microsoft.com/download/A/E/9/AE984CD4-CF4B-41E7-9ABD-6735E3F01897/MicrosoftTeamsCustomerSuccessKit.zip)をダウンロードして、プレゼンテーション、サンプル メール、ポスター、および使用開始ガイドを入手してください。


5.  従業員のインターネット アクセスと帯域幅が、Teams のために十分なものであることを確認します。 これを行う方法については、「[Teams 用に組織のネットワークを準備する](prepare-network.md)」のガイダンスをご覧ください。
    - 帯域幅が十分でない場合、Teams 会議の音質に影響を与える可能性があります。 低帯域幅の条件下での会議エクスペリエンスを最良なものにするために、ビデオの使用を控え、通話と会議の音声に公衆交換電話網 (PSTN) を使用することをユーザーに推奨します。 

    - 通話や会議の品質に関する問題のトラブルシューティングや解決のサポートが必要な場合は、この記事の下部にある「[既知の問題: Skype for Business/Teams 会議 ID へのダイヤルイン](#known-issue-dialing-into-skype-for-business-or-teams-conference-ids)」のガイダンスに従ってください。

2.  [トレーニングへのリンクを送信](enduser-training.md)して、従業員が Teams を最大限に活用できるよう支援します。
    
3. リモートでの作業に関する Microsoft の新しいコンテンツを読み、ユーザーと共有します。
        
      - Teams ブログ (2020 年 2 月 28 日): [Microsoft Teams を使用して在宅勤務するための 4 つのヒント](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/4-tips-for-working-from-home-with-microsoft-teams-by-lola/ba-p/1202083)

      - [Office 365 で共同作業する](https://support.office.com/article/Collaborate-with-Office-365-ac05a41e-0b49-4420-9ebc-190ee4e744f4)

      - [Teams と Office 365 を使用してリモートで作業する](https://support.microsoft.com/help/4549995/working-remotely-with-teams-and-office-365)

3.  モバイル アプリを[インストール](get-clients.md#mobile-clients)して使用することを全従業員に奨励します: [iOS](https://go.microsoft.com/fwlink/?LinkId=835758)   [Android](https://go.microsoft.com/fwlink/p/?linkid=2102168)

    > [!NOTE]
    > 中国にお住まいの場合は、「[中国で Android 用 Teams を取得する](get-teams-android-in-china.md)」にアクセスしてください

4.  ユーザーの問い合わせに対応するために [ヘルプ デスク](troubleshoot-installation.md)の人員を増やします。


## <a name="communications"></a>コミュニケーション

Teams を使用して、従業員と連絡を取り合います。
- [組織全体のチーム](create-an-org-wide-team.md)、および[社内コミュニケーター](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates#company-communicator) アプリのテンプレート
    
- 組織の在宅勤務および健康と安全に関するポリシーに関する情報を送信します。
    
- 全社的な会議および活動には、[ライブ イベント](teams-live-events/what-are-teams-live-events.md)を使用します。 参加者が 250 人以上の会議は、ライブ イベントにします。 

## <a name="personal-considerations"></a>社員が心がけるべきこと

在宅勤務を成功させるためのヒントを次に示します。

- 明るく、適切なエルゴノミクスを備えた、他のスペースから区別された物理的な作業スペースを確保します。

- 勤務時間や在席予定時間を明確に決め、不在時は Teams の[プレゼンス状態](https://support.office.com/article/change-your-status-in-teams-ce36ed14-6bc9-4775-a33e-6629ba4ff78e)を使用してそのことを示します。

- 在宅勤務でも意識的に「通勤」します。在宅勤務をすることで、在宅中イコール勤務時間にならないように気をつけてください。

- 定期的に立ち上がり、休憩をとります。 散歩やストレッチをしたりお茶を飲んだりして休みます。

## <a name="known-issue-dialing-into-skype-for-business-or-teams-conference-ids"></a>既知の問題: Skype for Business または Teams 会議 ID へのダイヤルイン

以下は、2020 年 2 月 7 日のメッセージ センターの投稿 (MC203397) の概要です。

Microsoft では、中国地域の一部のユーザーが Skype for Business または Teams 会議 ID にダイヤルインする際に問題が発生していることを認識しています。 ほとんどの場合、これらの問題は、Microsoft が管理するシステムの外部で発生しています。 多くの場合、問題はローカルのモバイル キャリアおよびテレフォニー キャリアにあります。 

電話会議の問題が発生した場合は、次のことをお勧めします。

- 発信者または会議の開催者にユーザーの PSTN または携帯電話の電話番号に発信することを依頼する
- VoIP を使用して、デスクトップまたはモバイル クライアントから電話や会議に参加する

サポート チケットを記録する必要がある場合は、次の情報を入力してください。
    
- 通話の正確な時間
- ダイヤルされた会議ブリッジ番号
- 発信者の電話ネットワーク
- 発信者の電話番号
