---
title: バージョンのサポート
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
ms.collection: M365-voice
localization_priority: Normal
description: この記事では、Microsoft Teams のルームのライフサイクルのサポートについて説明します。
ms.openlocfilehash: d06a3e78bba07e09a8df46d57b3c18cc8473dea1
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243313"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft Teams 室アプリバージョンのサポート
 
Microsoft Teams の会議室の更新プログラムは、毎年、一般的な利用可能時間 (GA) から12か月の各更新プログラムでサポートされています。 テクニカルサポートは12ヶ月全体に対応しています。 ただし、現在のサポート構造は動的で、最新バージョンの可用性に依存する2つの異なるサービスフェーズに進化しています。

**サービスと重要な更新プログラムのサービスフェーズ**\-最新バージョンの Microsoft Teams ルームを実行している場合は、セキュリティとサービスの更新プログラムを含む定期的な更新プログラムを受け取ることになります。

**セキュリティ更新プログラム (のみ) サービスフェーズ**\-新しいバージョンがリリースされた後、古いブランチのサポートは、12ヶ月のサービス更新プログラムのサポートライフサイクルの残りの部分に対してのみセキュリティ更新プログラムを提供します。

> [!NOTE]
> 最新バージョンは、常にサービスと重要な更新のサービスフェーズに含まれています。 つまり、重要な更新プログラムを提供するコードの問題が発生した場合は、修正プログラムを受け取るために最新バージョンがインストールされている必要があります。 サポートされているその他のすべてのバージョンは、セキュリティ更新プログラムを受け取ることができます。

すべてのサポートは、12ヶ月のバージョンのライフサイクルの有効期限が切れた後、または2つ以上の更新プログラムがリリースされてから終了します。 次に、お客様はサポートされているバージョンにアップデートする必要があります。

すべてのリリースは、 [Microsoft Teams ルームのリリースノート](srs2-release-note.md)に記載されています。

# <a name="os-version-support"></a>OS バージョンのサポート
Microsoft Teams のルームを実行しているデバイスの windows 10 の機能更新プログラムは、Windows がリリース更新を行った時点から6か月間は提供されません。 これを実現するには、Windows Update for Business channel (つまり、半期チャネル) とアプリの設定で Microsoft Teams 室デバイス用の特別なブロックを配置します。 このブロック期間中は、Microsoft Teams のアプリと周辺機器が接続されている Windows 10 の新機能リリースが、社内およびお客様のデバイスの OEM パートナーによって、さまざまなテストを行っていることを確認します。 これは、デバイスのセキュリティと一貫性のあるユーザーエクスペリエンスを保証し、Microsoft Teams の会議アプリを通じて提供されるエクスペリエンスの品質を確実にするために重要です。 

(つまり、これらのデバイスでダウンロードするための Windows 10 機能更新プログラムが用意されています) 時点では、Microsoft Teams の会議では、アプリサポートポリシーを使用して、12か月分の特定の Windows 10 機能リリースがサポートされています。 Windows 10 の機能更新プログラムは6か月ごとに提供されるため、これにより、Microsoft Teams では、現在のバージョンのサポートが終了するまでの2つのリリースが追加されています。 これは、Windows 10 バージョンが6か月ごとにブロック解除されることも意味します。 アプリは、ブロックされている最後の Windows リリースに対して継続的に変化し、開発されます。 Microsoft Teams 室のデバイスで発生した問題について、アプリの修正プログラムを確実に入手するために、すべてのユーザーに対して、サポートされている windows バージョンのガイダンスに収められるように、これらのデバイスを最新の Windows 10 の機能更新プログラムにアップグレードすることをお勧めします。

このように、Microsoft Teams の会議室デバイスでは、サポートされている最小バージョンの2019から、Windows 10 バージョン1709が必要です。 Windows 10 バージョン1703またはそれ以降のシステムでは、新しいアプリのリリースは提供されません。

> [!NOTE]
> Microsoft Teams の会議室デバイスが次のバージョンの Windows 10 OS と互換性がある場合、デバイスは Windows Update を通じて次のバージョンに自動的に更新されます。 Microsoft Teams 室のデバイスは、Windows 10 の次のリリースに手動で、または Windows Update for Business (WUFB) グループポリシーを使用して、"受信する更新プログラムの Windows の準備レベルを選択してください" と "選択してください" を使用してアップグレードしないでください。プレビュービルドと機能更新プログラムは、「GPO を通じて」オプションを受け取ります。 これらのグループポリシーを有効にすることで、Windows 10 OS 更新プログラムと Microsoft Teams 室アプリの間で問題が発生する可能性があることがわかっています。 
 
<a name="See"> </a> 
## <a name="see-also"></a>関連項目

[Microsoft Teams Rooms ヘルプ](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams のルームリリースノート](srs2-release-note.md)

[Microsoft Teams のルームを計画する](skype-room-systems-v2-0.md)
