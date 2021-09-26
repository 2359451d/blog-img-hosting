# Content

* [Content](#content)
* [Instruction](#instruction)
* [Upload Content](#upload-content)
* [Delete Content](#delete-content)

# Instruction

API Refer:

https://docs.github.com/en/rest/reference/repos#create-or-update-file-contents

https://developer.github.com/v3/repos/contents/

# Upload Content

Postman Example

![](/static/2021-09-26-23-02-42.png)

URL

* `PUT https://api.github.com/repos/{user}/{project}/contents/{path}`
* `PUT https://api.github.com/repos/2359451d/blog-img-hosting/contents/images/testUUID1.png`

Headers

```txt
Accept:application/vnd.github.v3+json

Authorization:token {TOKEN_VALUE}
```

Request body

```json
{
  "message": "{commit info}",
  "committer": {
    "name": "2359451d",
    "email": "2359451d@student.gla.ac.uk"
  },
  "content":"{file BASE64-encoding str}"
}
```

---

Response

```json
{
    "content": {
        "name": "testUUID2.png",
        "path": "images/testUUID2.png",
        "sha": "2bb1c0a08efb0063d13638c5bf053f93c81a42bf",
        "size": 480877,
        "url": "https://api.github.com/repos/2359451d/blog-img-hosting/contents/images/testUUID2.png?ref=main",
        "html_url": "https://github.com/2359451d/blog-img-hosting/blob/main/images/testUUID2.png",
        "git_url": "https://api.github.com/repos/2359451d/blog-img-hosting/git/blobs/2bb1c0a08efb0063d13638c5bf053f93c81a42bf",
        "download_url": "https://raw.githubusercontent.com/2359451d/blog-img-hosting/main/images/testUUID2.png",
        "type": "file",
        "_links": {
            "self": "https://api.github.com/repos/2359451d/blog-img-hosting/contents/images/testUUID2.png?ref=main",
            "git": "https://api.github.com/repos/2359451d/blog-img-hosting/git/blobs/2bb1c0a08efb0063d13638c5bf053f93c81a42bf",
            "html": "https://github.com/2359451d/blog-img-hosting/blob/main/images/testUUID2.png"
        }
    },
    "commit": {
        "sha": "afc74a93cb4d0bb6363401081d7c6f1e3069fe82",
        "node_id": "C_kwDOGHhl2NoAKGFmYzc0YTkzY2I0ZDBiYjYzNjM0MDEwODFkN2M2ZjFlMzA2OWZlODI",
        "url": "https://api.github.com/repos/2359451d/blog-img-hosting/git/commits/afc74a93cb4d0bb6363401081d7c6f1e3069fe82",
        "html_url": "https://github.com/2359451d/blog-img-hosting/commit/afc74a93cb4d0bb6363401081d7c6f1e3069fe82",
        "author": {
            "name": "2359451d",
            "email": "2359451d@student.gla.ac.uk",
            "date": "2021-09-26T15:10:15Z"
        },
        "committer": {
            "name": "2359451d",
            "email": "2359451d@student.gla.ac.uk",
            "date": "2021-09-26T15:10:15Z"
        },
        "tree": {
            "sha": "cb2dc4a8193bc02a77c4775bf3914019744ace49",
            "url": "https://api.github.com/repos/2359451d/blog-img-hosting/git/trees/cb2dc4a8193bc02a77c4775bf3914019744ace49"
        },
        "message": "test",
        "parents": [
            {
                "sha": "5755de3fef2f62ce2b609f1e66dabd74613d73fe",
                "url": "https://api.github.com/repos/2359451d/blog-img-hosting/git/commits/5755de3fef2f62ce2b609f1e66dabd74613d73fe",
                "html_url": "https://github.com/2359451d/blog-img-hosting/commit/5755de3fef2f62ce2b609f1e66dabd74613d73fe"
            }
        ],
        "verification": {
            "verified": false,
            "reason": "unsigned",
            "signature": null,
            "payload": null
        }
    }
}
```

# Delete Content

Postman Example

![](/static/2021-09-26-23-33-44.png)

URL

* `DELETE /repos/{owner}/{repo}/contents/{path}`
* `DELETE https://api.github.com/repos/2359451d/blog-img-hosting/contents/images/testUUID2.png`

Headers

```txt
Accept:application/vnd.github.v3+json

Authorization:token {TOKEN_VALUE}
```

Request body

* sha：Required. The blob SHA of the file being replaced.

```json
{
    "message": "delete testUUID2.png",
    "sha": "2bb1c0a08efb0063d13638c5bf053f93c81a42bf"
}
```

---

Response

```json
{
    "content": null,
    "commit": {
        "sha": "c13c7414888044fd281e48d34033b0739f3c1248",
        "node_id": "C_kwDOGHhl2NoAKGMxM2M3NDE0ODg4MDQ0ZmQyODFlNDhkMzQwMzNiMDczOWYzYzEyNDg",
        "url": "https://api.github.com/repos/2359451d/blog-img-hosting/git/commits/c13c7414888044fd281e48d34033b0739f3c1248",
        "html_url": "https://github.com/2359451d/blog-img-hosting/commit/c13c7414888044fd281e48d34033b0739f3c1248",
        "author": {
            "name": "Yao Du",
            "email": "46606028+2359451d@users.noreply.github.com",
            "date": "2021-09-26T15:32:46Z"
        },
        "committer": {
            "name": "Yao Du",
            "email": "46606028+2359451d@users.noreply.github.com",
            "date": "2021-09-26T15:32:46Z"
        },
        "tree": {
            "sha": "a2c7df631e95ca3a8769b262bf9d90cdb7372cb7",
            "url": "https://api.github.com/repos/2359451d/blog-img-hosting/git/trees/a2c7df631e95ca3a8769b262bf9d90cdb7372cb7"
        },
        "message": "delete testUUID2.png",
        "parents": [
            {
                "sha": "afc74a93cb4d0bb6363401081d7c6f1e3069fe82",
                "url": "https://api.github.com/repos/2359451d/blog-img-hosting/git/commits/afc74a93cb4d0bb6363401081d7c6f1e3069fe82",
                "html_url": "https://github.com/2359451d/blog-img-hosting/commit/afc74a93cb4d0bb6363401081d7c6f1e3069fe82"
            }
        ],
        "verification": {
            "verified": false,
            "reason": "unsigned",
            "signature": null,
            "payload": null
        }
    }
}
```