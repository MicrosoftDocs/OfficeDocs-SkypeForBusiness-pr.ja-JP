---
title: Microsoft 365 Multi-Geo 対応環境での Teams のエクスペリエンス
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: この記事では、Microsoft 365 Multi-Geo 対応環境での Teams の使用について説明します。
ms.openlocfilehash: 43abe221c6159e6dfed1705f5cbc4839c1ce57db
ms.sourcegitcommit: 93d84e172cb4b19acde4b8bae9b77efe96c44c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122247"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Microsoft 365 Multi-Geo 対応テナントでの Teams のエクスペリエンス

Microsoft Teams は、Microsoft 365 および Office 365 のチームワークのハブです。 Microsoft 365 Groups サービスを利用し、SharePoint Online や OneDrive for Business でファイルを使用できます。 テナントが北米、ヨーロッパ、オーストラリアなどの多くの地理的な場所に拡張される OneDrive for Business/SharePoint Online Multi-Geo テナントでは、基になるファイル エクスペリエンスはマルチジオ対応なので、Teams でのファイルの共同作業のエクスペリエンスもマルチジオ対応です。 この機能は、Teams がネイティブ ファイル エクスペリエンスで複数の地域でホストされているファイルを表示するための主要な最先端機能です。 これには、OneNote ファイルと Wiki ファイルも含まれます。

たとえば、Contoso テナントでは、ヨーロッパを衛星地域として、北米を中心地域として使用している場合、ヨーロッパの衛星ユーザーは、左側のウィンドウの [ファイル] タブの下に OneDrive ファイルが表示されます。ただし、ファイルはヨーロッパのデータの場所でホストされ、米国はテナントの中心的な場所です。 また、ユーザーは [最近使ったビュー] ブレードの下で、最近使用した **ファイルに** アクセスできます。 最近使用したファイルには、他の地域のユーザーから共有されたファイルが含まれる場合があります。 

特定のチームの SharePoint サイトも、複数の地域を認識しています。 つまり、ヨーロッパの衛星ユーザーがチームを作成している場合、対応する SharePoint サイトがヨーロッパの場所に作成されます。 そのチームに関連付けられているファイルは、その場所に保存されます。 新しいファイルのアップロードやファイルの編集など、その後のエクスペリエンスはヨーロッパの場所に保存され、それらのファイルに対するデータ常駐の約束が保たれるでしょう。

複数地域テナントは 1 つのグローバル テナントなので、@ メンションの間、衛星ユーザーは、場所に関係なく、世界中の同僚を見る可能性があります。

Teams エクスペリエンス内のチャット、チャネル メッセージ、会議 IM ノート/チャット内の会話は、マルチジオ対応ではなんらテナントの中心的な場所にのみ保存されます。 通常、チャットの会話はデータ常駐のニーズには適用されません。 詳細については [、「Microsoft Teams のデータの場所」を参照してください](location-of-data-in-teams.md)。

Multi-Geo の詳細については [、Microsoft Multi-Geo](https://aka.ms/multi-geo)の機能ページを参照してください。
