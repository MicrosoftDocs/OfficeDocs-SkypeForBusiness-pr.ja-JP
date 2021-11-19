---
title: 安全なメッセージングのための、Teams セキュリティのベスト プラクティス
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 11/10/2021
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: Teams を安全に使用する方法に関するクイック リファレンスです。この記事は、セキュリティに関する一般的なベスト プラクティスへの入門と、安全なメッセージングに関するユーザーのトレーニングに関するヒントとしてお使いいただけます。
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 61ba1607f2999ef56c3176d4ba8ed0aaebb82e50
ms.sourcegitcommit: 115e44f33fc7993f6eb1bc781f83eb02a506e29b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2021
ms.locfileid: "60909682"
---
# <a name="security-best-practices-for-microsoft-teams"></a>Microsoft Teams のためのセキュリティのベスト プラクティス

インスタント メッセージングとビデオ会議を通じたコラボレーションにより、多くの業界や学校は、パンデミック中もその業務の継続が許されました。 ただし、このような広範な規模でのオンラインのリアルタイム コラボレーションには、警告されるべき *リスク* も伴います。 警告されなければ、悪いふるまいをする人は、**フィッシング詐欺** や **スパム** キャンペーンを使用して、この仕事や生活の変化を悪用しようとします。 この記事の番号付きリファレンス リストは、Teams を使用して他のユーザーにメッセージを送信する際の、一般的なセキュリティの入門としてお使い頂くことができ、また Teams その他のインスタント メッセージングの新規ユーザー向けのセキュリティに関するトレーニング ガイダンスとしてもお使いいただけます。

電子メールに存在するのと同じフィッシング リスクがインスタント メッセージングとコラボレーション アプリに存在します。そのため、ユーザーへの啓発とガイダンスは、Teams ユーザーを安全に保護するために、適用されるべきです。

ユーザー レベルでは、一部の指標はシンプルにすることができ、ユーザーはそのルールを信頼することで、自信が感じられるべきです。 ユーザーは、「[フィッシング詐欺から自分を保護する](https://support.microsoft.com/en-us/windows/protect-yourself-from-phishing-0c7ea947-ba98-3bd9-7184-430e1f860a44)」の記事に示されている通り、知らないユーザーや本人確認ができないユーザーからのリンクをクリックして開くべきではありません。 また、外部からの攻撃に対して保護するために、[外部アクセスの管理 (フェデレーション) - Microsoft Teams | Microsoft Docs](/microsoftteams/manage-external-access)について考慮しながら、テナント管理者はエンタープライズ フェデレーションと Teams for Life (TFL) と Skype の相互運用性を無効またはオフにすることができます。

この Teams コラボレーション機能セットを使用すると、メッセージング、ファイルの共同作業、会議、ホワイトボードなど、その他数多くのコネクトする機会が得られます。 これらの機能は、Teams for Enterprise、Teams for Life、Skype、Skype for Business、Azure Communication Services (ACS)、その他に渡って機能します。 つまり、これらの能力の豊かさを越えて、自分自身、同僚、そして顧客を保護する必要があることを意味します。 ここで、繰り返し申し上げますが、すべてのユーザーは、自分自身、同僚、そして顧客のために最も安全な決定を下す能力を与えられる必要があります。

## <a name="just-as-with-email-online-safety-must-be-practiced-in-microsoft-teams-messaging"></a>まさに電子メールと同様に、オンラインの安全性は Microsoft Teams メッセージングで実践されるべきです。

標準的な安全指標は Teams で作業している時にこそ根付かせるべきです。

1. 組織外からの連絡や会議出席依頼に対して、ご用念ください。 見知らぬ人は、悪気のない存在になりえます。 また、一部は密かに悪意を持っているかもしれません。
2. あなたが送信者を認識できない場合は、会社の既知のグローバル アドレス一覧で 送信者のID を確認し、確認できない通信を上位レベルに通報トして対処します。 疑いがある場合は、不明なユーザーや未確認のユーザーとのやり取りをしてはいけません。
3. 不明なユーザーからリンクまたはファイルを受け取った場合は、そのリンクをクリックしてはいけません。 繰り返しになりますが、ご自身のための最善の判断を用い、また他のユーザーやあなたの顧客の安全に関する最善の判断を用います。
4. クリックしたリンク ナビゲーションから、ナビゲーションによって禁止されている、安全なリンク ページに移動した場合は、そのページの回避を試みないでください (クリックした添付ファイルが赤色で、安全な添付ファイル ページが禁止されている場合も同様です)。 ターゲット サイトは既知で信頼している場合は、問題をあなたの上司と Microsoft に報告して下さい。 ただし、禁止ページに導かれる理由は多数あるので、赤いフラグは迂回するのではなく、思慮する必要があります。
5. 依頼した覚えのない要請に対して、決して個人情報を提供してはいけません。 これもまた、個人の安全に対するリスクです。 詳細情報は、あなたの誕生日と同じくらい単純に、攻撃者によって悪用されうるものです。
6. リンクをスキャンして、疑わしいスペル、追加された数字、または奇妙な文字を検索します。 `www.litware.com/strategies/Metricsbreakout.xlsx`のようなリンクを期待するかもしれませんが、しかし`www.litwre.com`のようなアドレス、`www.litwarecom.com`や`www.litwαre.com`でさえ、見つかります。 リンクが識別できない場合は、疑うべきです。 アドレス `www.litware.com` は `www.litware2021.com` と同じではありません。

常に用心を心がけること、油断をせず、また同僚の油断を軽視せず、また了承しない、これを維持継続することは重要です。 責任あるユーザーとして、あなたが信頼を置く前に、検証することを以て、あなた自身、その同僚や顧客を守る自信を得たと感じるべきです。

最後に、すべてのユーザーが間違うことを認識することは極めて重要です。 ユーザーは、急いでいた場合や、疲れているときなど、クリックしやすくなります。 管理者は、問題あるリンクのクリックや、その他のセキュリティ インシデントの報告先のリソースは、組織のユーザーに明瞭に知られている必要があり、そうであれば、ミスが発生した場合にユーザーはリソースを知っていて、その後のセキュリティ対応が可能です。

> [!TIP]
> 特にメールが会社の外部からである場合 (たとえば、組織が *Litware* ではなく、*@litware.com* で終わるアカウントなど)、不明な連絡先のプロファイル カードを確認します。 ユーザーは、**(GUEST)** のためのプロファイル カードをチェックして、知らないユーザーがゲストとして会議に参加しているのかどうかを確認できます。 ゲストは明示的に参加者として招待されます。