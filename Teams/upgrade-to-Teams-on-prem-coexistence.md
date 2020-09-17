---
title: Skype for Business オンプレミス展開から Teams へのアップグレード - Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Skype for Business から Teams へのアップグレード
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 11252c916224393c19ebc11c4c40faceab02342c
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940719"
---
# <a name="coexistence-with-teams-and-skype-for-business"></a>Teams と Skype for Business の共存

この記事では、どのモードやどのアップグレード方法を使用しているかに関係なく、同じ組織内で Teams と Skype for Business クライアントの両方を実行しているときに発生する可能性のある動作について説明します。

- [会議](#meetings)
- [相互運用性](#interoperability)
- [Teams の会話 - 相互運用とネイティブ スレッドの違い](#teams-conversations---interop-versus-native-threads)
- [プレゼンス](#presence)
- [フェデレーション](#federation)
- [連絡先](#contacts)



## <a name="meetings"></a>会議

モードに関係なく、ユーザーは、Skype for Business であれ Teams であれ、招待されたすべての種類の会議にいつでも参加できます。  ただし、ユーザーは、会議の種類に合った対応するクライアントを使用してその会議に参加する必要があります。

- 会議が Teams 会議の場合、参加者全員 (TeamsOnly、アイランド、Skype for Business のいずれのユーザーであっても) が、Teams クライアントを使用して会議に参加します。 Teams がインストールされていない場合、そのユーザーが会議に参加しようとすると、Web に移動されます。

- 会議が Skype for Business 会議の場合、参加者全員 (TeamsOnly、アイランド、Skype for Business のいずれのユーザーであっても) が、Skype for Business クライアントを使用して会議に参加します。 Skype for Business クライアントがインストールされていない場合、そのユーザーは、Skype 会議アプリ経由で参加できるように Web に移動されます。

会議を開催する場合、スケジュールされる会議の種類は、次の表に示すように開催者のモードに基づいて決定されます。

| 開催者のモード    |      動作 |
| :------------------ | :---------------- |
| TeamsOnly、SfbWithTeamsCollabAndMeetings |    すべての会議が Teams でスケジュールされます。 Skype for Business アドインは Outlook では使用できません。 | 
| SfbWithTeamsCollab、SfbOnly   | すべての会議が Skype for Business でスケジュールされます。 Teams アドインは Outlook では使用できません。 | 
| アイランド | 既定では、会議は Skype for Business または Teams のいずれかでスケジュールできます。 両方のアドインを Outlook で使用できます。 ただし、必要に応じて、TeamsMeetingPolicy のインスタンスを PreferredMeetingProviderForIslandsMode = Teams で割り当てることによって、島々のユーザーに常に Teams の会議をスケジュールするように要求することができます。| 


## <a name="interoperability"></a>相互運用性

Teams では、特定のシナリオで Skype for Business との相互運用性をサポートしています。 相互運用通信とは、Skype for Business ユーザーと Teams ユーザーとの間のチャットや通話を意味しています。  相互運用通信は、2 人のユーザー間でのみ可能です。マルチパーティ チャットや通信、別のユーザーを追加することはサポートされていません。

2 人のユーザー間での相互運用チャットや通信は、次の各条件が満たされている場合に作成されます。

- 一方のユーザーは Teams を使用し、他方のユーザーは Skype for Business を使用している。

- どちらも同じ組織内のユーザーである場合は、最初の通信の受信者のモードがアイランドではない (アイランド モードの場合、通信は同一のクライアントに配信される)。 フェデレーション シナリオの場合、送信側のユーザーは Teams を使用しており、受信者は TeamsOnly モードではない。 

- Teams ユーザーは、オンプレミスに所属している Skype for Business アカウントも所有してはいない。 

相互運用通信では、チャットはプレーンテキストのみです。 また、*相互運用チャット自体*では、ファイル共有や画面共有は行えません。 ただし、次のようにして相互運用チャット内からオンデマンド会議を作成することにより、相互運用会話中のユーザーは簡単にファイル共有や画面共有を実現できます。

- Teams ユーザーが画面を共有しようとすると、オンデマンドの Teams 会議が自動的に作成され、Skype for Business ユーザーのクライアントにその会議への招待リンクが送信されます。 リンクをクリックすると、Skype for Business ユーザーの Teams が開き、会議に参加できます。 これで、両方のユーザーが Teams 会議に参加する形になり、必要に応じて共有を行なえます。

- Skype for Business ユーザーが 2018 以降のクライアントを使用していて、任意のコンテンツを共有しようとすると、オンデマンドの Skype for Business 会議が自動的に作成され、Teams ユーザーのクライアントにその会議への招待リンクが送信されます。 リンクをクリックすると、Teams ユーザーがその Skype for Business 会議に参加するための試行が実行されます。 その Teams ユーザーが Skype for Business クライアントをインストール済みの場合は、そのクライアントが開き、ユーザーはログインするように求められます (ログインしていない場合)。  その Teams ユーザーが Skype for Business クライアントをインストールしていない場合は、Web バージョンを使用するように求められます。 両方のユーザーがログインすると、どちらも Skype for Business 会議に参加している形になり、必要に応じて共有を行なえます。

## <a name="teams-conversations---interop-versus-native-threads"></a>Teams の会話 - 相互運用とネイティブ スレッドの違い

相互運用通信はネイティブな Teams の会話の一部の機能をサポートしていないため、Teams クライアントは、"Teams から Teams" の通信と "Teams から Skype for Business" の通信の会話スレッドを別個に維持します。 これらの会話は、ユーザー インターフェイスに異なる方法で表示されます。相互運用スレッドは、通常のネイティブな Teams スレッドと次の点で区別できます。

- リッチ テキスト、ファイル/画面共有、ユーザー追加禁止のコントロールが表示されない。
- ターゲット ユーザーのアイコンが変更され、Skype for Business を意味する S が表示される。

これらの違いを次のスクリーンショットに示します。

ユーザー G3 Test とのネイティブな "Teams から Teams" の会話

![ネイティブな "Teams から Teams" の会話を示す図](media/teams-upgrade-native-thread.png)

同じユーザー G3 Test との相互運用会話

![相互運用の "Teams から Teams" の会話を示す図](media/teams-upgrade-interop-thread.png)

会話スレッドが一旦作成されると、その種類は変更されません。 作成された Teams の相互運用スレッドは、常にターゲット ユーザーの Skype for Business クライアントにルーティングされます。 ネイティブ スレッドは、常にターゲット ユーザーの Teams クライアントにルーティングされます。  受信者ユーザーのモードが変わると、そのユーザーに対する既存の Teams スレッドは機能しなくなり、次のスクリーンショットに示すように、メモと、ネイティブな会話を新たに始めるためのリンクがそのチャット上に表示されます。


![アップグレードした Skype for Business ユーザーとのチャットを示す図](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

## <a name="presence"></a>プレゼンス

特定のユーザーのプレゼンスは、クライアントを介したサービスでのユーザーのアクティビティに基づきます。 プレゼンスは、他のユーザーが表示できるように公開されます。  Skype for Business と Teams は、別個のクライアントを持つ別個のサービスなので、各サービスはユーザーに関する独自のプレゼンス状態を持ちます。   Teams と Skype for Business Online のプレゼンス サービスの間では、同期も行われます。  これにより、必要に応じて一方のサービスが他方のサービスからユーザーのプレゼンスを公開することが可能になります。 

プレゼンスの公開動作は、ユーザーのモードに基づいて決定されます。 次の 3 つの基本的なケースがあります。

- ユーザーが TeamsOnly モードの場合、他のすべてのユーザーには、使用するクライアントに関係なく、そのユーザーの Teams プレゼンスが表示されます。

- ユーザーが Skype for Business のいずれかのモードの場合、他のすべてのユーザーには、使用するクライアントに関係なく、そのユーザーの Skype for Business プレゼンスが表示されます。

- ユーザーがアイランド モードの場合、Skype for Business と Teams で公開されるプレゼンスは独立しているため、同一組織内のユーザーに表示されるプレゼンスは、相手側ユーザーのクライアントによって決まります。 フェデレーション組織のユーザーには、Skype for Business のアクティビティに基づいてそのユーザーのプレゼンスが表示されます。これは、アイランド モードのユーザーに対するフェデレーション トラフィックが Skype for Business に配信されるためです。

たとえば、ユーザー A がアイランド モードであるとします。 ユーザー A が Teams ではアクティブで Skype for Business にはサインインしていない場合、他のユーザーには、Teams クライアントからはユーザー A はアクティブであるように見えますが、Skype for Business クライアントではユーザー A はオフラインであるように見えます。 これは仕様です。クライアントを実行していない場合、ユーザー A にはアクセスできません。 


## <a name="federation"></a>フェデレーション

Skype for Business を使用している他のユーザーへの Teams からのフェデレーションには、Teams ユーザーが Skype for Business のオンラインに所属している必要があります。 TeamsUpgradePolicy は、着信するフェデレーションされたチャットと通話のルーティングを制御します。 フェデレーションされたルーティングの動作は、同じテナントの場合のシナリオと同じものです (アイランド モードの場合を除く)。 受信者がアイランド モードの場合の動作は、次のようになります。

- Teams から開始されたチャットと通話は、受信者がフェデレーションされたテナントにいる場合、Skype for Business に配信されます。
- Teams から開始されたチャットと通話は、受信者が同じテナントにいる場合、Teams に配信されます。
- Skype for Business から開始されたチャットと通話は常に、Skype for Business に配信されます。

フェデレーションされたチャットは、ネイティブスレッドまたは相互運用スレッドのいずれかになります。 「 [チームの会話---相互運用機能とネイティブスレッド](#teams-conversations---interop-versus-native-threads)」をご覧ください。

- 受信者と送信者が両方ともチームのアップグレードモードである場合、会話はネイティブのチャットエクスペリエンスになり、すべての豊富なメッセージング機能と通話機能が含まれます。 詳細については、「 [Teams の外部 (フェデレーション) ユーザー向けのネイティブチャットの操作」](native-chat-for-external-users.md)を参照してください。 

- いずれかの会話参加者がチームのアップグレードモードになっていない場合、会話はテキストのみのメッセージでの相互運用機能の操作環境のままです。 ユーザー インターフェイスには、そのユーザーが外部ユーザーであることを示すメモがあることを除けば、同一テナントの相互運用スレッドと同様の方法でフェデレーション チャットが表示されます。

詳細については、「 [Microsoft teams で外部アクセスを管理](manage-external-access.md) する」および「 [teams の外部 (フェデレーション) ユーザー向けのネイティブチャットの操作](native-chat-for-external-users.md)」を参照してください。

## <a name="contacts"></a>連絡先

Teams と Skype for Business は、連絡先の別個のリストを保持します。 これは、一方のシステムでなされた連絡先の追加、削除、変更が、他方のシステムには同期されないことを意味します。 ただし、次の 2 つの特定のイベントのどちらかが発生すると、Skype for Business の連絡先が Teams に自動的にコピーされます。 

- Skype for Business Online ユーザーが初めて Teams にログオンすると、Skype for Business の連絡先が Teams にコピーされます。  この動作は、Skype for Business Server のオンプレミス アカウントを持つユーザーには利用できません。  

- ユーザーが TeamsOnly にアップグレードされ (TeamsUpgradePolicy を割り当てるか Move-CsUser -MoveToTeams で) た後に、次にユーザーが Teams にログインすると、Skype for Business の既存の連絡先が Teams の既存の連絡先とマージされます。 この動作は、ユーザーの Skype for Business アカウントがオンプレミスかオンラインである場合に発生します。 

どちらの場合も、Skype for Business から Teams への連絡先の転送は非同期なので、連絡先が Teams に表示されるまでに数分かかることがあります。 上述の 2 つのイベントがコピーをトリガーします。  

## <a name="related-links"></a>関連リンク

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](migration-interop-guidance-for-teams-with-skype.md) 

[Skype for Business Server と Microsoft 365 または Office 365 間のハイブリッド接続を構成する](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[オンプレミスとクラウドの間でユーザーを移動する](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[共存およびアップグレードを設定する](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[会議移行サービス (MMS) を使用する](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

