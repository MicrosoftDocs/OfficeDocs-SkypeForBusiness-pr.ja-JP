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
description: このガイダンスは、特に新型コロナウイルス感染症 (COVID-19) の大流行に対応して在宅勤務 (WFH) している場合に、組織のリモート ワーカーが Microsoft Teams を使用して生産性を向上できるようにします。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4fbdb875896ca07402d699f1ca2a28770cb46ee2
ms.sourcegitcommit: ae65fb089d98665c4b26e0345bb96241fb893f0b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/29/2020
ms.locfileid: "42342904"
---
# <a name="support-remote-workers-using-microsoft-teams"></a>Microsoft Teams を使用してリモート ワーカーをサポートする

この記事に記載されているベスト プラクティスを使用して、リモートまたは自宅で作業しているユーザーをサポートします。

## <a name="technical"></a>テクニカル

1.  [すべてのユーザーに対して Teams が有効になっている](assign-teams-licenses.md)ことを確認する
    
      - [[Teams Exploratory](teams-exploratory.md)] または [[Teams (無料)](https://support.office.com/article/Welcome-to-Microsoft-Teams-free-6d79a648-6913-4696-9237-ed13de64ae3c)] を見て、社内の全員が Teams を利用できるようにします。

      - リモートの従業員は、会議や電話会議に大きく依存しています。 これらのワークロードをまだ展開していない場合は、「[Teams での会議](deploy-meetings-microsoft-teams-landing-page.md)」をご覧ください。

2.  Teams についてユーザーに通知します。 [ Teams カスタマー サクセス キット](https://download.microsoft.com/download/A/E/9/AE984CD4-CF4B-41E7-9ABD-6735E3F01897/MicrosoftTeamsCustomerSuccessKit.zip)をダウンロードして、プレゼンテーション、サンプル メール、ポスター、および入門ガイドを入手してください。


5.  従業員に Teams のために十分なインターネット アクセスと帯域幅があることを確認します。 これを行う方法については、「[Teams 用に組織のネットワークを準備する](prepare-network.md)」のガイダンスを使用してください。
    - 帯域幅の制限は、Teams 会議の音質に影響を与える可能性があります。 低帯域幅の条件下で最高の会議エクスペリエンスを確保するには、ビデオを制限し、通話と会議の音声に PSTN を使用するようユーザーに推奨します。 

    - 通話や会議の品質に関する問題のトラブルシューティングや修正のサポートが必要な場合は、この記事の下部にある「[既知の問題: Skype for Business/Teams 会議 ID へのダイヤル](#known-issue-dialing-into-skype-for-business-or-teams-conference-ids)」のガイダンスに従ってください。

2.  [トレーニングへのリンクを送信](enduser-training.md)して、従業員が Teams を最大限に活用できるようにします。
    
3. リモートでの作業に関する新しいコンテンツを読み、ユーザーと共有します。
        
      - Teams ブログ (2020 年 2 月 28 日): [Microsoft Teams を使用して在宅勤務するための 4 つのヒント](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/4-tips-for-working-from-home-with-microsoft-teams-by-lola/ba-p/1202083)

      - [Office 365 で共同作業する](https://support.office.com/article/Collaborate-with-Office-365-ac05a41e-0b49-4420-9ebc-190ee4e744f4)

      - [Teams および Office 365 を使用してリモートで作業する](https://support.microsoft.com/help/4549995/working-remotely-with-teams-and-office-365)

3.  全員がモバイル アプリを[インストール](get-clients.md#mobile-clients)して使用するように勧める: [iOS](https://go.microsoft.com/fwlink/?LinkId=835758)   [Android](https://go.microsoft.com/fwlink/p/?linkid=2102168)

    > [!NOTE]
    > 中国にお住まいの場合は、「[中国で Android 用 Teams を取得する](get-teams-android-in-china.md)」にアクセスしてください

4.  ユーザーの問い合わせに対応するために [ヘルプ デスク](troubleshoot-installation.md)の人員を増やします。


## <a name="communications"></a>コミュニケーション

Teams を使用して、従業員と連絡を取り合います。
- [組織全体のチーム](create-an-org-wide-team.md)、および[社内コミュニケーター](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates#company-communicator)のアプリ テンプレート
    
- 組織の在宅勤務、正常性、および安全に関するポリシーに関する情報を送信します。
    
- 全社的な会議および活動には、[[ライブ イベント](teams-live-events/what-are-teams-live-events.md)] を使用します。 250 人を超える参加者の会議は、ライブ イベントにします。 

## <a name="personal-considerations"></a>個人的な考慮事項

在宅勤務を成功させるためのヒントを次に示します。

- 良好な照明と適切なエルゴノミクスを備えた明確な物理的作業スペースを確保します。

- 勤務時間とコミットメントに明確な境界線を設定し、Teams の[プレゼンス状態](https://support.office.com/article/change-your-status-in-teams-ce36ed14-6bc9-4775-a33e-6629ba4ff78e)を使用して、不在の時期を示します。

- 在宅勤務でも意識的に「通勤」します。在宅勤務で自宅を職場のように変えないでください。

- 定期的に起きて休憩をとります。 散歩に行って、ストレッチして、お茶を飲みます。

## <a name="known-issue-dialing-into-skype-for-business-or-teams-conference-ids"></a>既知の問題: Skype for Business または Teams 会議 ID へのダイヤル

以下は、2020 年 2 月 7 日のメッセージ センターの投稿 (MC203397) の概要です。

Microsoft は、中国地域の一部のユーザーが Skype for Business または Teams 会議 ID にダイヤルする際に問題が発生していることを認識しています。 ほとんどの場合、これらの問題は、管理下にあるシステムの外部にあります。 多くの場合、問題はローカルのモバイル キャリアおよびテレフォニー キャリアにあります。 

電話会議の問題が発生した場合は、次のことをお勧めします。

- 相手または会議の開催者に PSTN または携帯電話の電話番号を依頼する
- VoIP を使用して、デスクトップまたはモバイル クライアントから電話や会議に参加する

サポート チケットを記録する必要がある場合は、次の情報を入力してください。
    
- 通話の正確な時間
- ダイヤルする会議ブリッジ番号
- 発信者の電話ネットワーク
- 発信者の電話番号
