Eloqua SDK for Java
=================
A software development kit for Java that helps developers build applications that integrate with Eloqua.
Currently contains clients for the Bulk API.

## Bulk Client Project
### Create Client
	AccountInfo info = BulkClient.GetAccountInfo("site", "user", "password");
	String baseUrl = info.urls.apis.rest.bulk;

### GET (list)
	SearchResponse<Field> fields = client.ContactFieldClient().Search(searchTerm, page, count);	

### Contact Export
	Export export = new Export
	{
		name = "sample export",
		fields = fields,
		filter = filter,
		secondsToAutoDelete = 3600,
		secondsToRetainData = 3600,
		syncActions = new List<SyncAction>
						{
							new SyncAction
								{
									action = SyncActionType.add,
									destinationUri = destinationUri
								}
						}
	};
	
## License
	Copyright [2013] [Fred Sakr]
	Licensed under the Apache License, Version 2.0 (the "License");
	you may not use this file except in compliance with the License.
	You may obtain a copy of the License at
	http://www.apache.org/licenses/LICENSE-2.0
	Unless required by applicable law or agreed to in writing, software
	distributed under the License is distributed on an "AS IS" BASIS,
	WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
	See the License for the specific language governing permissions and
	limitations under the License.