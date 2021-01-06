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
ms.openlocfilehash: 1a1689d78f6ce4e35b2e632e4a46ff0ec23a0d15
ms.sourcegitcommit: 7575fb476a594d70084c603e508dd311ef1d7edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49757752"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Microsoft 365 Multi-Geo 対応テナントでの Teams のエクスペリエンス

Microsoft Teams は、Microsoft 365 のチームワークのハブであるグループ チャット ソフトウェアです。 Microsoft 365 Groups サービスを利用し、SharePoint や OneDrive と共にファイルのエクスペリエンスを提供します。 テナントが北米、ヨーロッパ、オーストラリアなどの多くの地理的な場所に拡張されている複数地域の組織では、基になるファイル エクスペリエンスはマルチジオを認識しています。そのため、ファイルの共同作業に関する Teams のエクスペリエンスも複数地域対応です。 これにより、Teams はネイティブ ファイル エクスペリエンスで複数の地理的な場所にホストされているファイルを表示できます。

たとえば、Contoso テナントでは、ヨーロッパを衛星地域として、北米を中心地域として使用している場合、ヨーロッパの衛星ユーザーには、左側のウィンドウの [ファイル] タブの下に OneDrive ファイルが表示されます。ただし、ファイルはヨーロッパのデータの場所でホストされ、米国はテナントの中心的な場所です。 また、ユーザーは [最近使ったビュー] ブレードの下で、最近使用したファイルにアクセスできます。 最近使用したファイルには、他の地域のユーザーから共有されたファイルが含まれる場合があります。 

特定のチームの SharePoint サイトも複数の地域を認識しています。 つまり、ヨーロッパの衛星ユーザーがチームを作成している場合、対応する SharePoint サイトはヨーロッパの場所に作成され、そのチームに関連付けられているファイルは、その場所に保存されます。 新しいファイルのアップロードやファイルの編集など、その後のエクスペリエンスはヨーロッパの場所に保存され、それらのファイルに対するデータ常駐の約束が保たれるでしょう。

Teams エクスペリエンス内のチャットや会議 IM ノート内の会話は、複数地域を認識しているのではなく、すべて組織内の中心的な場所にのみ保持されます。

複数地域の詳細については [、Microsoft Multi-Geo の機能を参照してください](https://aka.ms/multi-geo)。
