openapi: 3.0.1
info:
  title: '[API] Account service'
  description: List api user
  version: 1.0-SNAPSHOT
tags:
- name: auth-controller
  description: contain auth api
- name: department-controller
  description: Department Controller
- name: health-controller
  description: Health Controller
- name: location-controller
  description: Location Controller
- name: permission-controller
  description: Permission Controller
- name: role-controller
  description: Role Controller
- name: user-controller
  description: User Controller
paths:
  /auth/check-token:
    post:
      tags:
      - auth-controller
      summary: checkToken
      operationId: checkTokenUsingPOST
      requestBody:
        description: token
        content:
          application/json:
            schema:
              type: string
        required: true
      responses:
        200:
          description: OK
          content:
            '*/*':
              schema:
                type: object
        201:
          description: Created
          content: {}
        401:
          description: You are not authorized to view the resource
          content: {}
        403:
          description: Accessing the resource you were trying to reach is forbidden
          content: {}
        404:
          description: Not Found
          content: {}
        500:
          description: Internal Server Error
          content: {}
      x-codegen-request-body-name: token
  /auth/confirm-account/{token}:
    get:
      tags:
      - auth-controller
      summary: confirmAccount
      operationId: confirmAccountUsingGET
      parameters:
      - name: token
        in: path
        description: token
        required: true
        schema:
          type: string
      responses:
        200:
          description: OK
          content:
            '*/*':
              schema:
                type: object
        401:
          description: You are not authorized to view the resource
          content: {}
        403:
          description: Accessing the resource you were trying to reach is forbidden
          content: {}
        404:
          description: Not Found
          content: {}
        500:
          description: Internal Server Error
          content: {}
  /auth/find/{username}:
    get:
      tags:
      - auth-controller
      summary: findByEmailOrPhone
      operationId: findByEmailOrPhoneUsingGET
      parameters:
      - name: username
        in: path
        description: username
        required: true
        schema:
          type: string
      responses:
        200:
          description: OK
          content:
            '*/*':
              schema:
                type: object
        401:
          description: You are not authorized to view the resource
          content: {}
        403:
          description: Accessing the resource you were trying to reach is forbidden
          content: {}
        404:
          description: Not Found
          content: {}
        500:
          description: Internal Server Error
          content: {}
  /auth/forget-password:
    post:
      tags:
      - auth-controller
      summary: Forget password
      operationId: forgetPasswordUsingPOST
      requestBody:
        description: email
        content:
          application/json:
            schema:
              type: string
        required: true
      responses:
        200:
          description: Thao tác thành công
          content:
            '*/*':
              schema:
                type: object
        201:
          description: Created
          content: {}
        401:
          description: You are not authorized to view the resource
          content: {}
        403:
          description: Accessing the resource you were trying to reach is forbidden
          content: {}
        404:
          description: Not Found
          content: {}
        500:
          description: Internal Server Error
          content: {}
      x-codegen-request-body-name: email
  /auth/login:
    post:
      tags:
      - auth-controller
      summary: Login authenticate
      operationId: loginUsingPOST
      requestBody:
        description: loginReqDto
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/LoginReqDTO'
        required: true
      responses:
        200:
          description: Thao tác thành công
          content:
            '*/*':
              schema:
                type: object
        201:
          description: Created
          content: {}
        401:
          description: You are not authorized to view the resource
          content: {}
        403:
          description: Accessing the resource you were trying to reach is forbidden
          content: {}
        404:
          description: Not Found
          content: {}
        500:
          description: Internal Server Error
          content: {}
      x-codegen-request-body-name: loginReqDto
  /auth/refresh-token:
    post:
      tags:
      - auth-controller
      summary: Refresh token authenticate
      operationId: refreshUserPrincipalTokenUsingPOST
      requestBody:
        description: refreshTokenReqDto
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/RefreshTokenReqDTO'
        required: true
      responses:
        200:
          description: Thao tác thành công
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/TokenResDTO'
        201:
          description: Created
          content: {}
        401:
          description: You are not authorized to view the resource
          content: {}
        403:
          description: Accessing the resource you were trying to reach is forbidden
          content: {}
        404:
          description: Not Found
          content: {}
        500:
          description: Internal Server Error
          content: {}
      x-codegen-request-body-name: refreshTokenReqDto
  /auth/reset-password:
    put:
      tags:
      - auth-controller
      summary: Reset password
      operationId: resetPasswordUsingPUT
      requestBody:
        description: dto
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/ResetPasswordDTO'
        required: true
      responses:
        200:
          description: Thao tác thành công
          content:
            '*/*':
              schema:
                type: object
        201:
          description: Created
          content: {}
        401:
          description: You are not authorized to view the resource
          content: {}
        403:
          description: Accessing the resource you were trying to reach is forbidden
          content: {}
        404:
          description: Not Found
          content: {}
        500:
          description: Internal Server Error
          content: {}
      x-codegen-request-body-name: dto
  /auth/signup:
    post:
      tags:
      - auth-controller
      summary: signUp
      operationId: signUpUsingPOST
      requestBody:
        description: params
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/AuthUserDto'
        required: true
      responses:
        200:
          description: OK
          content:
            '*/*':
              schema:
                type: object
        201:
          description: Created
          content: {}
        401:
          description: You are not authorized to view the resource
          content: {}
        403:
          description: Accessing the resource you were trying to reach is forbidden
          content: {}
        404:
          description: Not Found
          content: {}
        500:
          description: Internal Server Error
          content: {}
      x-codegen-request-body-name: params
  /auth/verify/{token}:
    get:
      tags:
      - auth-controller
      summary: verifyUser
      operationId: verifyUserUsingGET
      parameters:
      - name: token
        in: path
        description: token
        required: true
        schema:
          type: string
      responses:
        200:
          description: OK
          content:
            '*/*':
              schema:
                type: object
        401:
          description: You are not authorized to view the resource
          content: {}
        403:
          description: Accessing the resource you were trying to reach is forbidden
          content: {}
        404:
          description: Not Found
          content: {}
        500:
          description: Internal Server Error
          content: {}
  /auth/webapi/user:
    get:
      tags:
      - user-controller
      summary: getAll
      operationId: getAllUsingGET
      parameters:
      - name: currentPage
        in: query
        schema:
          type: integer
          format: int32
      - name: emailOrPhone
        in: query
        schema:
          type: string
      - name: filter
        in: query
        schema:
          type: string
      - name: fullname
        in: query
        schema:
          type: string
      - name: loginId
        in: query
        schema:
          type: string
      - name: perPage
        in: query
        schema:
          type: integer
          format: int32
      - name: roleId
        in: query
        schema:
          type: integer
          format: int32
      - name: sortBy
        in: query
        schema:
          type: string
      - name: sortDesc
        in: query
        schema:
          type: boolean
      - name: unitId
        in: query
        schema:
          type: string
      - name: userType
        in: query
        schema:
          type: integer
          format: int32
      - name: userTypes
        in: query
        style: form
        explode: true
        schema:
          type: array
          items:
            type: integer
            format: int32
      responses:
        200:
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/AuthenResponseModel'
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
        404:
          description: Not Found
          content: {}
    post:
      tags:
      - user-controller
      summary: Thêm mới user
      operationId: createUsingPOST
      parameters:
      - name: roleGroupIds
        in: query
        description: roleGroupIds
        schema:
          type: string
      requestBody:
        description: dto
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/UserModel'
        required: true
      responses:
        200:
          description: Thao tác thành công
          content:
            '*/*':
              schema:
                type: object
        201:
          description: Created
          content: {}
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
        404:
          description: Not Found
          content: {}
      x-codegen-request-body-name: dto
  /auth/webapi/user/active/{id}:
    post:
      tags:
      - user-controller
      summary: activeUser
      operationId: activeUserUsingPOST
      parameters:
      - name: id
        in: path
        description: id
        required: true
        schema:
          type: integer
          format: int32
      responses:
        200:
          description: OK
          content:
            '*/*':
              schema:
                type: object
        201:
          description: Created
          content: {}
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
        404:
          description: Not Found
          content: {}
  /auth/webapi/user/byLoginId/{loginId}:
    put:
      tags:
      - user-controller
      summary: update
      operationId: updateUsingPUT_1
      parameters:
      - name: loginId
        in: path
        description: loginId
        required: true
        schema:
          type: string
      - name: roleGroupIds
        in: query
        description: roleGroupIds
        schema:
          type: string
      requestBody:
        description: dto
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/UserModel'
        required: true
      responses:
        200:
          description: OK
          content:
            '*/*':
              schema:
                type: object
        201:
          description: Created
          content: {}
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
        404:
          description: Not Found
          content: {}
      x-codegen-request-body-name: dto
  /auth/webapi/user/change-password:
    put:
      tags:
      - user-controller
      summary: changePassword
      operationId: changePasswordUsingPUT
      requestBody:
        description: dto
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/ChangePasswordModel'
        required: true
      responses:
        200:
          description: OK
          content:
            '*/*':
              schema:
                type: object
        201:
          description: Created
          content: {}
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
        404:
          description: Not Found
          content: {}
      x-codegen-request-body-name: dto
  /auth/webapi/user/current:
    put:
      tags:
      - user-controller
      summary: updateCurrentUser
      operationId: updateCurrentUserUsingPUT
      requestBody:
        description: dto
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/UserModel'
        required: true
      responses:
        200:
          description: OK
          content:
            '*/*':
              schema:
                type: object
        201:
          description: Created
          content: {}
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
        404:
          description: Not Found
          content: {}
      x-codegen-request-body-name: dto
  /auth/webapi/user/deactive/{id}:
    post:
      tags:
      - user-controller
      summary: deactiveUser
      operationId: deactiveUserUsingPOST
      parameters:
      - name: id
        in: path
        description: id
        required: true
        schema:
          type: integer
          format: int32
      requestBody:
        description: request
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/UserDeactiveReasonModel'
        required: true
      responses:
        200:
          description: OK
          content:
            '*/*':
              schema:
                type: object
        201:
          description: Created
          content: {}
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
        404:
          description: Not Found
          content: {}
      x-codegen-request-body-name: request
  /auth/webapi/user/{id}:
    get:
      tags:
      - user-controller
      summary: getOne
      operationId: getOneUsingGET
      parameters:
      - name: id
        in: path
        description: id
        required: true
        schema:
          type: integer
          format: int32
      responses:
        200:
          description: OK
          content:
            '*/*':
              schema:
                type: object
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
        404:
          description: Not Found
          content: {}
    put:
      tags:
      - user-controller
      summary: update
      operationId: updateUsingPUT
      parameters:
      - name: id
        in: path
        description: id
        required: true
        schema:
          type: integer
          format: int32
      requestBody:
        description: dto
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/UserModel'
        required: true
      responses:
        200:
          description: OK
          content:
            '*/*':
              schema:
                type: object
        201:
          description: Created
          content: {}
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
        404:
          description: Not Found
          content: {}
      x-codegen-request-body-name: dto
    delete:
      tags:
      - user-controller
      summary: delete
      operationId: deleteUsingDELETE
      parameters:
      - name: id
        in: path
        description: id
        required: true
        schema:
          type: integer
          format: int32
      responses:
        200:
          description: OK
          content:
            '*/*':
              schema:
                type: object
        204:
          description: No Content
          content: {}
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
  /departments:
    get:
      tags:
      - department-controller
      summary: Lấy thông tin toàn bộ đơn vị bán hàng
      operationId: findAllDepartmentUsingGET
      responses:
        200:
          description: Thao tác thành công
          content:
            '*/*':
              schema:
                type: object
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
        404:
          description: Not Found
          content: {}
    post:
      tags:
      - department-controller
      summary: Thêm mới đơn vị bán hàng
      operationId: createDepartmentUsingPOST
      requestBody:
        description: departmentCreateDTO
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/DepartmentCreateDTO'
        required: true
      responses:
        200:
          description: Thao tác thành công
          content:
            '*/*':
              schema:
                type: object
        201:
          description: Created
          content: {}
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
        404:
          description: Not Found
          content: {}
      x-codegen-request-body-name: departmentCreateDTO
  /departments/search:
    post:
      tags:
      - department-controller
      summary: Tìm kiếm đơn vị bán hàng theo điều kiện
      operationId: findDepartmentByConditionUsingPOST
      requestBody:
        description: sdSearchReqDTO
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/SaleDepartmentSearchReqDTO'
        required: true
      responses:
        200:
          description: Thao tác thành công
          content:
            '*/*':
              schema:
                type: object
        201:
          description: Created
          content: {}
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
        404:
          description: Not Found
          content: {}
      x-codegen-request-body-name: sdSearchReqDTO
  /departments/{departmentId}:
    put:
      tags:
      - department-controller
      summary: Update thông tin đơn vị
      operationId: updateDepartmentUsingPUT
      parameters:
      - name: departmentId
        in: path
        description: departmentId
        required: true
        schema:
          type: integer
          format: int32
      requestBody:
        description: departmentUpdateDTO
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/DepartmentUpdateDTO'
        required: true
      responses:
        200:
          description: Thao tác thành công
          content:
            '*/*':
              schema:
                type: object
        201:
          description: Created
          content: {}
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
        404:
          description: Not Found
          content: {}
      x-codegen-request-body-name: departmentUpdateDTO
    delete:
      tags:
      - department-controller
      summary: Xóa đơn vị
      operationId: deleteDepartmentUsingDELETE
      parameters:
      - name: departmentId
        in: path
        description: departmentId
        required: true
        schema:
          type: integer
          format: int32
      responses:
        200:
          description: Thao tác thành công
          content:
            '*/*':
              schema:
                type: object
        204:
          description: No Content
          content: {}
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
  /departments/{department_id}/detail:
    get:
      tags:
      - department-controller
      summary: Xem chi tiết thông tin đơn vị
      operationId: findDepartmentByIdUsingGET
      parameters:
      - name: department_id
        in: path
        description: department_id
        required: true
        schema:
          type: integer
          format: int32
      responses:
        200:
          description: Thao tác thành công
          content:
            '*/*':
              schema:
                type: object
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
        404:
          description: Not Found
          content: {}
  /health:
    get:
      tags:
      - health-controller
      summary: Check Health
      operationId: checkHealthUsingGET
      responses:
        200:
          description: Thao tác thành công
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseEntity'
        401:
          description: You are not authorized to view the resource
          content: {}
        403:
          description: Accessing the resource you were trying to reach is forbidden
          content: {}
        404:
          description: Not Found
          content: {}
        500:
          description: Internal Server Error
          content: {}
  /locations:
    get:
      tags:
      - location-controller
      summary: Lấy thông tin tỉnh/ TP
      operationId: findLocationUsingGET
      responses:
        200:
          description: Thao tác thành công
          content:
            '*/*':
              schema:
                type: object
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
        404:
          description: Not Found
          content: {}
  /permissions:
    post:
      tags:
      - permission-controller
      summary: Thêm mới thông tin permission
      operationId: createPermissionUsingPOST
      requestBody:
        description: permissionCreateReqDTO
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/PermissionCreateReqDTO'
        required: true
      responses:
        200:
          description: Thao tác thành công
          content:
            '*/*':
              schema:
                type: object
        201:
          description: Created
          content: {}
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
        404:
          description: Not Found
          content: {}
      x-codegen-request-body-name: permissionCreateReqDTO
  /permissions/search:
    post:
      tags:
      - permission-controller
      summary: Tìm kiếm permission theo điều kiện
      operationId: findPermissionByConditionUsingPOST
      requestBody:
        description: permissionSearchReqDTO
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/PermissionSearchReqDTO'
        required: true
      responses:
        200:
          description: Thao tác thành công
          content:
            '*/*':
              schema:
                type: object
        201:
          description: Created
          content: {}
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
        404:
          description: Not Found
          content: {}
      x-codegen-request-body-name: permissionSearchReqDTO
  /permissions/{permission_id}:
    get:
      tags:
      - permission-controller
      summary: Xem chi tiết thông tin permission
      operationId: findPermissionByIdUsingGET
      parameters:
      - name: permission_id
        in: path
        description: permission_id
        required: true
        schema:
          type: integer
          format: int32
      responses:
        200:
          description: Thao tác thành công
          content:
            '*/*':
              schema:
                type: object
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
        404:
          description: Not Found
          content: {}
    put:
      tags:
      - permission-controller
      summary: Update thông tin permission
      operationId: updatePermissionUsingPUT
      parameters:
      - name: permission_id
        in: path
        description: permission_id
        required: true
        schema:
          type: integer
          format: int32
      requestBody:
        description: permissionUpdateReqDTO
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/PermissionUpdateReqDTO'
        required: true
      responses:
        200:
          description: Thao tác thành công
          content:
            '*/*':
              schema:
                type: object
        201:
          description: Created
          content: {}
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
        404:
          description: Not Found
          content: {}
      x-codegen-request-body-name: permissionUpdateReqDTO
    delete:
      tags:
      - permission-controller
      summary: Xóa permission
      operationId: deletePermissionByIdUsingDELETE
      parameters:
      - name: permission_id
        in: path
        description: permission_id
        required: true
        schema:
          type: integer
          format: int32
      responses:
        200:
          description: Thao tác thành công
          content:
            '*/*':
              schema:
                type: object
        204:
          description: No Content
          content: {}
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
  /roles:
    post:
      tags:
      - role-controller
      summary: Thêm mới thông tin role
      operationId: createRoleUsingPOST
      requestBody:
        description: roleCreateReqDTO
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/RoleCreateReqDTO'
        required: true
      responses:
        200:
          description: Thao tác thành công
          content:
            '*/*':
              schema:
                type: object
        201:
          description: Created
          content: {}
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
        404:
          description: Not Found
          content: {}
      x-codegen-request-body-name: roleCreateReqDTO
  /roles/search:
    post:
      tags:
      - role-controller
      summary: Tìm kiếm role theo điều kiện
      operationId: findRoleByConditionUsingPOST
      requestBody:
        description: roleSearchReqDTO
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/RoleSearchReqDTO'
        required: true
      responses:
        200:
          description: Thao tác thành công
          content:
            '*/*':
              schema:
                type: object
        201:
          description: Created
          content: {}
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
        404:
          description: Not Found
          content: {}
      x-codegen-request-body-name: roleSearchReqDTO
  /roles/{role_id}:
    get:
      tags:
      - role-controller
      summary: Xem chi tiết thông tin role
      operationId: findRoleByIdUsingGET
      parameters:
      - name: role_id
        in: path
        description: role_id
        required: true
        schema:
          type: integer
          format: int32
      responses:
        200:
          description: Thao tác thành công
          content:
            '*/*':
              schema:
                type: object
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
        404:
          description: Not Found
          content: {}
    put:
      tags:
      - role-controller
      summary: Update thông tin role
      operationId: updateRoleUsingPUT
      parameters:
      - name: role_id
        in: path
        description: role_id
        required: true
        schema:
          type: integer
          format: int32
      requestBody:
        description: roleUpdateReqDTO
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/RoleUpdateReqDTO'
        required: true
      responses:
        200:
          description: Thao tác thành công
          content:
            '*/*':
              schema:
                type: object
        201:
          description: Created
          content: {}
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
        404:
          description: Not Found
          content: {}
      x-codegen-request-body-name: roleUpdateReqDTO
    delete:
      tags:
      - role-controller
      summary: Xóa role
      operationId: deleteRoleByIdUsingDELETE
      parameters:
      - name: role_id
        in: path
        description: role_id
        required: true
        schema:
          type: integer
          format: int32
      responses:
        200:
          description: Thao tác thành công
          content:
            '*/*':
              schema:
                type: object
        204:
          description: No Content
          content: {}
        401:
          description: Unauthorized
          content: {}
        403:
          description: Forbidden
          content: {}
  /tenant/{tenantId}:
    get:
      tags:
      - tenant-controller
      operationId: doRetrieve
      parameters:
      - name: tenantId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    put:
      tags:
      - tenant-controller
      operationId: doUpdate
      parameters:
      - name: tenantId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/TenantDTO'
        required: true
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    delete:
      tags:
      - tenant-controller
      operationId: doDelete
      parameters:
      - name: tenantId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
  /tenant-user/{tenantId}/{userId}:
    get:
      tags:
      - user-tenant-controller
      operationId: doRetrieve_1
      parameters:
      - name: tenantId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      - name: userId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    put:
      tags:
      - user-tenant-controller
      operationId: doUpdate_1
      parameters:
      - name: tenantId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      - name: userId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/UserTenantDTO'
        required: true
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    delete:
      tags:
      - user-tenant-controller
      operationId: doDelete_1
      parameters:
      - name: tenantId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      - name: userId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
  /tenant-profile/{tenantProfileId}:
    get:
      tags:
      - tenant-profile-controller
      operationId: doRetrieve_2
      parameters:
      - name: tenantProfileId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    put:
      tags:
      - tenant-profile-controller
      operationId: doUpdate_2
      parameters:
      - name: tenantProfileId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/TenantProfileDTO'
        required: true
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    delete:
      tags:
      - tenant-profile-controller
      operationId: doDelete_2
      parameters:
      - name: tenantProfileId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
  /tenant-profile/default/{tenantProfileId}:
    put:
      tags:
      - tenant-profile-controller
      operationId: setDefault
      parameters:
      - name: tenantProfileId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
  /ota/{id}:
    get:
      tags:
      - ota-controller
      operationId: findPackageById
      parameters:
      - name: id
        in: path
        required: true
        schema:
          type: integer
          format: int32
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    put:
      tags:
      - ota-controller
      operationId: modifyPackage
      parameters:
      - name: id
        in: path
        required: true
        schema:
          type: integer
          format: int32
      - name: description
        in: query
        required: false
        schema:
          type: string
          default: ""
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    delete:
      tags:
      - ota-controller
      operationId: deletePackageById
      parameters:
      - name: id
        in: path
        required: true
        schema:
          type: integer
          format: int32
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
  /device/{deviceId}:
    get:
      tags:
      - device-controller
      operationId: doRetrieve_3
      parameters:
      - name: deviceId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    put:
      tags:
      - device-controller
      operationId: doUpdate_3
      parameters:
      - name: deviceId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/DeviceDTO'
        required: true
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    delete:
      tags:
      - device-controller
      operationId: doDelete_3
      parameters:
      - name: deviceId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
  /device-profile/{deviceProfileId}:
    get:
      tags:
      - device-profile-controller
      operationId: doRetrieve_4
      parameters:
      - name: deviceProfileId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    put:
      tags:
      - device-profile-controller
      operationId: doUpdate_4
      parameters:
      - name: deviceProfileId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/DeviceProfileDTO'
        required: true
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    delete:
      tags:
      - device-profile-controller
      operationId: doDelete_4
      parameters:
      - name: deviceProfileId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
  /device-profile/delete/{deviceProfileId}:
    put:
      tags:
      - device-profile-controller
      operationId: setDelete
      parameters:
      - name: deviceProfileId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
  /device-profile/default/{deviceProfileId}:
    put:
      tags:
      - device-profile-controller
      operationId: setDefault_1
      parameters:
      - name: deviceProfileId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
  /device-attribute/{deviceAttributeId}:
    get:
      tags:
      - device-attribute-controller
      operationId: doRetrieve_5
      parameters:
      - name: deviceAttributeId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    put:
      tags:
      - device-attribute-controller
      operationId: doUpdate_5
      parameters:
      - name: deviceAttributeId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/DeviceAttributeDTO'
        required: true
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    delete:
      tags:
      - device-attribute-controller
      operationId: doDelete_5
      parameters:
      - name: deviceAttributeId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
  /customer/{customerId}:
    get:
      tags:
      - customer-controller
      operationId: doRetrieve_6
      parameters:
      - name: customerId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    put:
      tags:
      - customer-controller
      operationId: doUpdate_6
      parameters:
      - name: customerId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/CustomerDTO'
        required: true
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    delete:
      tags:
      - customer-controller
      operationId: doDelete_6
      parameters:
      - name: customerId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
  /customer-user/{customerId}/{userId}:
    get:
      tags:
      - user-customer-controller
      operationId: doRetrieve_7
      parameters:
      - name: customerId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      - name: userId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    put:
      tags:
      - user-customer-controller
      operationId: doUpdate_7
      parameters:
      - name: customerId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      - name: userId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/UserCustomerDTO'
        required: true
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    delete:
      tags:
      - user-customer-controller
      operationId: doDelete_7
      parameters:
      - name: customerId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      - name: userId
        in: path
        required: true
        schema:
          type: integer
          format: int32
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
  /tenant:
    get:
      tags:
      - tenant-controller
      operationId: doSearch
      parameters:
      - name: keyword
        in: query
        required: false
        schema:
          type: string
      - name: email
        in: query
        required: false
        schema:
          type: string
      - name: sortDesc
        in: query
        required: false
        schema:
          type: boolean
      - name: currentPage
        in: query
        required: false
        schema:
          type: integer
          format: int32
          default: 1
      - name: perPage
        in: query
        required: false
        schema:
          type: integer
          format: int32
          default: 10
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    post:
      tags:
      - tenant-controller
      operationId: doCreate
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/RequestModel'
        required: true
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
  /tenant-user:
    get:
      tags:
      - user-tenant-controller
      operationId: doSearch_1
      parameters:
      - name: tenantId
        in: query
        required: false
        schema:
          type: integer
          format: int32
      - name: keyword
        in: query
        required: false
        schema:
          type: string
      - name: currentPage
        in: query
        required: false
        schema:
          type: integer
          format: int32
          default: 1
      - name: perPage
        in: query
        required: false
        schema:
          type: integer
          format: int32
          default: 10
      - name: sortDesc
        in: query
        required: false
        schema:
          type: boolean
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    post:
      tags:
      - user-tenant-controller
      operationId: doCreate_1
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/RequestModel'
        required: true
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
  /tenant-profile:
    get:
      tags:
      - tenant-profile-controller
      operationId: doSearch_2
      parameters:
      - name: keyword
        in: query
        required: false
        schema:
          type: string
      - name: sortDesc
        in: query
        required: false
        schema:
          type: boolean
      - name: currentPage
        in: query
        required: false
        schema:
          type: integer
          format: int32
          default: 1
      - name: perPage
        in: query
        required: false
        schema:
          type: integer
          format: int32
          default: 10
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    post:
      tags:
      - tenant-profile-controller
      operationId: doCreate_2
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/RequestModel'
        required: true
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
  /ota:
    get:
      tags:
      - ota-controller
      operationId: getAllPackages
      parameters:
      - name: filter
        in: query
        required: false
        schema:
          type: string
          default: ""
      - name: limit
        in: query
        required: false
        schema:
          type: integer
          format: int32
          default: 20
      - name: offset
        in: query
        required: false
        schema:
          type: integer
          format: int32
          default: 1
      - name: sortDesc
        in: query
        required: false
        schema:
          type: boolean
          default: false
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    post:
      tags:
      - ota-controller
      operationId: createPackage
      requestBody:
        content:
          application/json:
            schema:
              required:
              - otaDTO
              type: object
              properties:
                otaDTO:
                  type: string
                file:
                  type: string
                  format: binary
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
  /device:
    get:
      tags:
      - device-controller
      operationId: doSearch_3
      parameters:
      - name: keyword
        in: query
        required: false
        schema:
          type: string
      - name: email
        in: query
        required: false
        schema:
          type: string
      - name: sortDesc
        in: query
        required: false
        schema:
          type: boolean
      - name: currentPage
        in: query
        required: false
        schema:
          type: integer
          format: int32
          default: 1
      - name: perPage
        in: query
        required: false
        schema:
          type: integer
          format: int32
          default: 10
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    post:
      tags:
      - device-controller
      operationId: doCreate_3
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/RequestModel'
        required: true
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
  /device-profile:
    get:
      tags:
      - device-profile-controller
      operationId: doSearch_4
      parameters:
      - name: keyword
        in: query
        required: false
        schema:
          type: string
      - name: sortDesc
        in: query
        required: false
        schema:
          type: boolean
      - name: currentPage
        in: query
        required: false
        schema:
          type: integer
          format: int32
          default: 1
      - name: perPage
        in: query
        required: false
        schema:
          type: integer
          format: int32
          default: 10
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    post:
      tags:
      - device-profile-controller
      operationId: doCreate_4
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/RequestModel'
        required: true
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
  /device-attribute:
    get:
      tags:
      - device-attribute-controller
      operationId: doSearch_5
      parameters:
      - name: keyword
        in: query
        required: false
        schema:
          type: string
      - name: deviceId
        in: query
        required: true
        schema:
          type: integer
          format: int32
      - name: sortDateDesc
        in: query
        required: false
        schema:
          type: boolean
      - name: sortKeyDesc
        in: query
        required: false
        schema:
          type: boolean
      - name: currentPage
        in: query
        required: false
        schema:
          type: integer
          format: int32
          default: 1
      - name: perPage
        in: query
        required: false
        schema:
          type: integer
          format: int32
          default: 10
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    post:
      tags:
      - device-attribute-controller
      operationId: doCreate_5
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/RequestModel'
        required: true
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
  /customer:
    get:
      tags:
      - customer-controller
      operationId: doSearch_6
      parameters:
      - name: keyword
        in: query
        required: false
        schema:
          type: string
      - name: sortDesc
        in: query
        required: false
        schema:
          type: boolean
      - name: currentPage
        in: query
        required: false
        schema:
          type: integer
          format: int32
          default: 1
      - name: perPage
        in: query
        required: false
        schema:
          type: integer
          format: int32
          default: 10
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    post:
      tags:
      - customer-controller
      operationId: doCreate_6
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/RequestModel'
        required: true
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
  /customer-user:
    get:
      tags:
      - user-customer-controller
      operationId: doSearch_7
      parameters:
      - name: customerId
        in: query
        required: false
        schema:
          type: integer
          format: int32
      - name: keyword
        in: query
        required: false
        schema:
          type: string
      - name: currentPage
        in: query
        required: false
        schema:
          type: integer
          format: int32
          default: 1
      - name: perPage
        in: query
        required: false
        schema:
          type: integer
          format: int32
          default: 10
      - name: sortDesc
        in: query
        required: false
        schema:
          type: boolean
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
    post:
      tags:
      - user-customer-controller
      operationId: doCreate_7
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/RequestModel'
        required: true
      responses:
        "200":
          description: OK
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/ResponseModel'
components:
  schemas:
    AuthUserDto:
      title: AuthUserDto
      type: object
      properties:
        email:
          type: string
        password:
          type: string
        username:
          type: string
    ChangePasswordModel:
      title: ChangePasswordModel
      type: object
      properties:
        newPassword:
          type: string
        oldPassword:
          type: string
    DepartmentCreateDTO:
      title: DepartmentCreateDTO
      type: object
      properties:
        Address:
          type: string
        Code:
          type: string
        LocationId:
          type: integer
          format: int32
        Name:
          type: string
        ParentId:
          type: integer
          format: int32
        RoleId:
          type: integer
          format: int32
        Status:
          type: string
        Type:
          type: string
    DepartmentInfoDTO:
      title: DepartmentInfoDTO
      type: object
      properties:
        Code:
          type: string
        CreatedAt:
          type: string
        DeletedAt:
          type: string
        IsDeleted:
          type: boolean
        LocationId:
          type: integer
          format: int32
        Name:
          type: string
        ParentId:
          type: integer
          format: int32
        Type:
          type: string
        UpdatedAt:
          type: string
        passWord:
          type: string
        status:
          type: string
        userName:
          type: string
    DepartmentUpdateDTO:
      title: DepartmentUpdateDTO
      type: object
      properties:
        Address:
          type: string
        Code:
          type: string
        LocationId:
          type: integer
          format: int32
        Name:
          type: string
        ParentId:
          type: integer
          format: int32
        RoleId:
          type: integer
          format: int32
        Status:
          type: string
        Type:
          type: string
        id:
          type: integer
          format: int32
    ListDepartmentDTO:
      title: ListDepartmentDTO
      type: object
      properties:
        content:
          type: array
          items:
            $ref: '#/components/schemas/SaleDepartmentResDTO'
        limit:
          type: integer
          format: int32
        offset:
          type: integer
          format: int64
        total:
          type: integer
          format: int64
    ListLocationDTO:
      title: ListLocationDTO
      type: object
      properties:
        content:
          type: array
          items:
            $ref: '#/components/schemas/LocationDTO'
        limit:
          type: integer
          format: int32
        offset:
          type: integer
          format: int64
        total:
          type: integer
          format: int64
    ListPermissionPageResDto:
      title: ListPermissionPageResDto
      type: object
      properties:
        content:
          type: array
          items:
            $ref: '#/components/schemas/PermissionInfoResDTO'
        limit:
          type: integer
          format: int32
        offset:
          type: integer
          format: int64
        total:
          type: integer
          format: int64
    ListRolePageResDto:
      title: ListRolePageResDto
      type: object
      properties:
        content:
          type: array
          items:
            $ref: '#/components/schemas/RoleInfoResDTO'
        limit:
          type: integer
          format: int32
        offset:
          type: integer
          format: int64
        total:
          type: integer
          format: int64
    LocationDTO:
      title: LocationDTO
      type: object
      properties:
        Code:
          type: string
        Id:
          type: integer
          format: int32
        Name:
          type: string
        ParentId:
          type: integer
          format: int32
    LoginReqDTO:
      title: LoginReqDTO
      type: object
      properties:
        password:
          type: string
        username:
          type: string
    Permission:
      title: Permission model
      type: object
      properties:
        activeFlag:
          type: integer
          format: int32
        code:
          type: string
        createdBy:
          type: integer
          format: int32
        createdDatetime:
          $ref: '#/components/schemas/Timestamp'
        description:
          type: string
        permissionAlias:
          type: string
        permissionId:
          type: integer
          format: int32
        permissionName:
          type: string
        updatedBy:
          type: integer
          format: int32
        updatedDatetime:
          $ref: '#/components/schemas/Timestamp'
    PermissionCreateReqDTO:
      title: PermissionCreateReqDTO
      type: object
      properties:
        code:
          type: string
        description:
          type: string
        permission_ids:
          type: array
          items:
            type: integer
            format: int32
        permission_name:
          type: string
    PermissionInfoResDTO:
      title: PermissionInfoResDTO
      type: object
      properties:
        active_flag:
          type: integer
          format: int32
        code:
          type: string
        created_by:
          type: string
        created_datetime:
          type: string
        permissionAlias:
          type: string
        permission_id:
          type: integer
          format: int32
        permission_name:
          type: string
        updated_by:
          type: string
        updated_datetime:
          type: string
    PermissionSearchReqDTO:
      title: PermissionSearchReqDTO
      type: object
      properties:
        description:
          type: string
        page:
          type: integer
          format: int32
        permission_ids:
          type: array
          items:
            type: integer
            format: int32
        permission_name:
          type: string
        size:
          type: integer
          format: int32
        sort:
          type: string
    PermissionUpdateReqDTO:
      title: PermissionUpdateReqDTO
      type: object
      properties:
        active_flag:
          type: integer
          format: int32
        description:
          type: string
        permission_ids:
          type: array
          items:
            type: integer
            format: int32
        permission_name:
          type: string
    RefreshTokenReqDTO:
      title: RefreshTokenReqDTO
      type: object
      properties:
        refreshToken:
          type: string
    ResetPasswordDTO:
      title: ResetPasswordDTO
      type: object
      properties:
        password:
          type: string
        token:
          type: string
    Response:
      title: Response
      type: object
      properties:
        code:
          type: integer
          format: int32
        data:
          type: object
          properties: {}
    ResponseEntity:
      title: ResponseEntity
      type: object
      properties:
        body:
          type: object
          properties: {}
        statusCode:
          type: string
          enum:
          - ACCEPTED
          - ALREADY_REPORTED
          - BAD_GATEWAY
          - BAD_REQUEST
          - BANDWIDTH_LIMIT_EXCEEDED
          - CHECKPOINT
          - CONFLICT
          - CONTINUE
          - CREATED
          - DESTINATION_LOCKED
          - EXPECTATION_FAILED
          - FAILED_DEPENDENCY
          - FORBIDDEN
          - FOUND
          - GATEWAY_TIMEOUT
          - GONE
          - HTTP_VERSION_NOT_SUPPORTED
          - IM_USED
          - INSUFFICIENT_SPACE_ON_RESOURCE
          - INSUFFICIENT_STORAGE
          - INTERNAL_SERVER_ERROR
          - I_AM_A_TEAPOT
          - LENGTH_REQUIRED
          - LOCKED
          - LOOP_DETECTED
          - METHOD_FAILURE
          - METHOD_NOT_ALLOWED
          - MOVED_PERMANENTLY
          - MOVED_TEMPORARILY
          - MULTIPLE_CHOICES
          - MULTI_STATUS
          - NETWORK_AUTHENTICATION_REQUIRED
          - NON_AUTHORITATIVE_INFORMATION
          - NOT_ACCEPTABLE
          - NOT_EXTENDED
          - NOT_FOUND
          - NOT_IMPLEMENTED
          - NOT_MODIFIED
          - NO_CONTENT
          - OK
          - PARTIAL_CONTENT
          - PAYLOAD_TOO_LARGE
          - PAYMENT_REQUIRED
          - PERMANENT_REDIRECT
          - PRECONDITION_FAILED
          - PRECONDITION_REQUIRED
          - PROCESSING
          - PROXY_AUTHENTICATION_REQUIRED
          - REQUESTED_RANGE_NOT_SATISFIABLE
          - REQUEST_ENTITY_TOO_LARGE
          - REQUEST_HEADER_FIELDS_TOO_LARGE
          - REQUEST_TIMEOUT
          - REQUEST_URI_TOO_LONG
          - RESET_CONTENT
          - SEE_OTHER
          - SERVICE_UNAVAILABLE
          - SWITCHING_PROTOCOLS
          - TEMPORARY_REDIRECT
          - TOO_EARLY
          - TOO_MANY_REQUESTS
          - UNAUTHORIZED
          - UNAVAILABLE_FOR_LEGAL_REASONS
          - UNPROCESSABLE_ENTITY
          - UNSUPPORTED_MEDIA_TYPE
          - UPGRADE_REQUIRED
          - URI_TOO_LONG
          - USE_PROXY
          - VARIANT_ALSO_NEGOTIATES
        statusCodeValue:
          type: integer
          format: int32
    AuthenResponseModel:
      title: AuthenResponseModel
      type: object
      properties:
        code:
          type: integer
          format: int32
        content:
          type: object
          properties: {}
        currentPage:
          type: integer
          format: int32
        errorMessages:
          type: string
        requestIdentifier:
          type: string
        totalPage:
          type: integer
          format: int32
        totalRecord:
          type: integer
          format: int32
    Role:
      title: Role model
      type: object
      properties:
        activeFlag:
          type: integer
          format: int32
        code:
          type: string
        createdBy:
          type: integer
          format: int32
        createdDatetime:
          type: string
          format: date-time
        description:
          type: string
        permissions:
          type: array
          items:
            $ref: '#/components/schemas/Permission'
        roleId:
          type: integer
          format: int32
        roleName:
          type: string
        updatedBy:
          type: integer
          format: int32
        updatedDatetime:
          type: string
          format: date-time
    RoleCreateReqDTO:
      title: RoleCreateReqDTO
      type: object
      properties:
        active_flag:
          type: integer
          format: int32
        code:
          type: string
        description:
          type: string
        permission_ids:
          type: array
          items:
            type: integer
            format: int32
        role_name:
          type: string
    RoleInfoResDTO:
      title: RoleInfoResDTO
      type: object
      properties:
        active_flag:
          type: integer
          format: int32
        code:
          type: string
        created_by:
          type: string
        created_datetime:
          type: string
        description:
          type: string
        permissions:
          type: array
          items:
            $ref: '#/components/schemas/PermissionInfoResDTO'
        role_id:
          type: integer
          format: int32
        role_name:
          type: string
        updated_by:
          type: string
        updated_datetime:
          type: string
    RoleSearchReqDTO:
      title: RoleSearchReqDTO
      type: object
      properties:
        description:
          type: string
        page:
          type: integer
          format: int32
        permission_ids:
          type: array
          items:
            type: integer
            format: int32
        role_name:
          type: string
        size:
          type: integer
          format: int32
        sort:
          type: string
    RoleUpdateReqDTO:
      title: RoleUpdateReqDTO
      type: object
      properties:
        active_flag:
          type: integer
          format: int32
        description:
          type: string
        permission_ids:
          type: array
          items:
            type: integer
            format: int32
        role_name:
          type: string
    SaleDepartmentDetailDTO:
      title: SaleDepartmentDetailDTO
      type: object
      properties:
        Address:
          type: string
        Code:
          type: string
        Id:
          type: integer
          format: int32
        LocationId:
          type: integer
          format: int32
        LocationName:
          type: string
        Name:
          type: string
        ParentId:
          type: integer
          format: int32
        ParentName:
          type: string
        RoleId:
          type: integer
          format: int32
        RoleName:
          type: string
        Status:
          type: string
    SaleDepartmentResDTO:
      title: SaleDepartmentResDTO
      type: object
      properties:
        Code:
          type: string
        Id:
          type: integer
          format: int32
        LocationName:
          type: string
        Name:
          type: string
        ParentName:
          type: string
        Status:
          type: string
        UserName:
          type: string
        parentId:
          type: integer
          format: int32
    SaleDepartmentSearchReqDTO:
      title: SaleDepartmentSearchReqDTO
      type: object
      properties:
        limit:
          type: integer
          format: int32
        locationId:
          type: integer
          format: int32
        name:
          type: string
        page:
          type: integer
          format: int32
        parentId:
          type: integer
          format: int32
    Timestamp:
      title: Timestamp
      type: object
      properties:
        date:
          type: integer
          format: int32
        day:
          type: integer
          format: int32
        hours:
          type: integer
          format: int32
        minutes:
          type: integer
          format: int32
        month:
          type: integer
          format: int32
        nanos:
          type: integer
          format: int32
        seconds:
          type: integer
          format: int32
        time:
          type: integer
          format: int64
        timezoneOffset:
          type: integer
          format: int32
        year:
          type: integer
          format: int32
    TokenResDTO:
      title: TokenResDTO
      type: object
      properties:
        accessToken:
          type: string
        code:
          type: integer
          format: int32
        content:
          type: object
          properties: {}
        currentPage:
          type: integer
          format: int32
        errorMessages:
          type: string
        expiredAccessToken:
          type: integer
          format: int64
        expiredRefreshToken:
          type: integer
          format: int64
        refreshToken:
          type: string
        requestIdentifier:
          type: string
        totalPage:
          type: integer
          format: int32
        totalRecord:
          type: integer
          format: int32
        userEntity:
          $ref: '#/components/schemas/UserEntity'
    UserDeactiveReasonModel:
      title: UserDeactiveReasonModel
      type: object
      properties:
        reason:
          type: string
    UserEntity:
      title: UserEntity
      type: object
      properties:
        address:
          type: string
        attempt_password:
          type: integer
          format: int32
        code:
          type: integer
          format: int32
        createdBy:
          type: integer
          format: int32
        createdDatetime:
          type: string
          format: date-time
        departmentId:
          type: integer
          format: int32
        description:
          type: string
        email:
          type: string
        fullName:
          type: string
        lastActive:
          type: string
          format: date-time
        password:
          type: string
        phoneNumber:
          type: string
        position:
          type: string
        roles:
          type: array
          items:
            $ref: '#/components/schemas/Role'
        status:
          type: string
          enum:
          - ACTIVE
          - DEACTIVE
          - WAITING
        tenantId:
          type: integer
          format: int32
        updatedBy:
          type: integer
          format: int32
        updatedDatetime:
          type: string
          format: date-time
        userId:
          type: integer
          format: int32
        username:
          type: string
        uuid:
          type: string
        verifyToken:
          type: string
        verifyTokenActive:
          type: boolean
        verifyTokenCreatedDate:
          type: string
          format: date-time
        verifyTokenExpiredDate:
          type: string
          format: date-time
    UserModel:
      title: UserModel
      type: object
      properties:
        accessKey:
          type: string
        address:
          type: string
        createdBy:
          type: integer
          format: int32
        createdDate:
          type: string
          format: date-time
        description:
          type: string
        email:
          type: string
        fullname:
          type: string
        id:
          type: integer
          format: int32
        lastActive:
          type: string
          format: date-time
        lockReason:
          type: string
        loginId:
          type: string
        password:
          type: string
        phone:
          type: string
        status:
          type: string
          enum:
          - ACTIVE
          - DEACTIVE
          - WAITING
        type:
          type: string
          enum:
          - SYSTEM_ADMIN
          - TENANT_ADMIN
          - TENANT_CUSTOMER
        unitId:
          type: string
        unitName:
          type: string
        updatedDate:
          type: string
          format: date-time
        verifyToken:
          type: string
        verifyTokenActive:
          type: boolean
        verifyTokenCreatedDate:
          type: string
          format: date-time
        verifyTokenExpiredDate:
          type: string
          format: date-time
    TenantDTO:
      type: object
      properties:
        tenantId:
          type: integer
          format: int32
        tenantName:
          type: string
        description:
          type: string
        phone:
          type: string
        email:
          type: string
        tenantProfileId:
          type: integer
          format: int32
        address:
          type: string
        createdDate:
          type: string
        createdBy:
          type: integer
          format: int32
        updatedDate:
          type: string
        updatedBy:
          type: integer
          format: int32
    ResponseModel:
      type: object
      properties:
        requestIdentifier:
          type: string
        code:
          type: integer
          format: int32
        errorMessages:
          type: string
        currentPage:
          type: integer
          format: int32
        totalRecord:
          type: integer
          format: int32
        totalPage:
          type: integer
          format: int32
        content:
          type: object
    UserTenantDTO:
      type: object
      properties:
        userId:
          type: integer
          format: int32
        tenantId:
          type: integer
          format: int32
        fullname:
          type: string
        userEmail:
          type: string
        phone:
          type: string
        description:
          type: string
        createdDate:
          type: string
        createdBy:
          type: integer
          format: int32
        updatedDate:
          type: string
    TenantProfileDTO:
      type: object
      properties:
        tenantProfileId:
          type: integer
          format: int32
        tenantProfileName:
          type: string
        description:
          type: string
        createdDate:
          type: string
          format: date-time
        createdBy:
          type: integer
          format: int32
        updatedDate:
          type: string
          format: date-time
        updatedBy:
          type: integer
          format: int32
        maxDeviceConf:
          type: integer
          format: int32
        maxCoreMsgNotify:
          type: integer
          format: int32
        maxMqttConnectTtl:
          type: integer
          format: int32
        apiRequestConf:
          type: integer
          format: int32
        maxDataStorageConf:
          type: integer
          format: int32
        isDefault:
          type: integer
          format: int32
    DeviceDTO:
      type: object
      properties:
        deviceId:
          type: integer
          format: int32
        deviceName:
          type: string
        deviceProfileId:
          type: integer
          format: int32
        isGateway:
          type: boolean
        customerId:
          type: integer
          format: int32
        label:
          type: string
        description:
          type: string
        createdDate:
          type: string
          format: date-time
        createdBy:
          type: integer
          format: int32
        updatedDate:
          type: string
          format: date-time
        updatedBy:
          type: integer
          format: int32
        tokenType:
          type: integer
          format: int32
        accessKey:
          type: string
        mqttClientId:
          type: string
        mqttUser:
          type: string
        mqttPass:
          type: string
    DeviceProfile:
      type: object
      properties:
        createdDate:
          type: string
          format: date-time
        updatedDate:
          type: string
          format: date-time
        deviceProfileId:
          type: integer
          format: int32
        deviceProfileName:
          type: string
        description:
          type: string
        deviceProfileLabel:
          type: string
        icon:
          type: object
          properties:
            binaryStream:
              type: object
        iconFileType:
          type: string
        protocol:
          type: string
        isDefault:
          type: integer
          format: int32
        isDeleted:
          type: integer
          format: int32
        createdBy:
          type: integer
          format: int32
        updatedBy:
          type: integer
          format: int32
    DeviceProfileDTO:
      type: object
      properties:
        deviceProfileId:
          type: integer
          format: int32
        deviceProfileName:
          type: string
        description:
          type: string
        deviceProfileLabel:
          type: string
        icon:
          type: string
        iconFileType:
          type: string
        protocol:
          type: string
        isDefault:
          type: integer
          format: int32
        createdDate:
          type: string
        createdBy:
          type: integer
          format: int32
        updatedDate:
          type: string
        updatedBy:
          type: integer
          format: int32
        entity:
          $ref: '#/components/schemas/DeviceProfile'
    DeviceAttribute:
      type: object
      properties:
        createdDate:
          type: string
          format: date-time
        updatedDate:
          type: string
          format: date-time
        deviceAttributeId:
          type: integer
          format: int32
        deviceAttributeName:
          type: string
        attributeKey:
          type: string
        attributeType:
          type: integer
          format: int32
        deviceId:
          type: integer
          format: int32
        attributeId:
          type: integer
          format: int32
        createdBy:
          type: integer
          format: int32
        updatedBy:
          type: integer
          format: int32
        isDeleted:
          type: boolean
    DeviceAttributeDTO:
      type: object
      properties:
        deviceAttributeId:
          type: integer
          format: int32
          writeOnly: true
        deviceAttributeName:
          type: string
        attributeKey:
          type: string
        attributeType:
          type: integer
          format: int32
        deviceId:
          type: integer
          format: int32
        attributeId:
          type: integer
          format: int32
        createdDate:
          type: string
        createdBy:
          type: integer
          format: int32
        updatedDate:
          type: string
        updatedBy:
          type: integer
          format: int32
        entity:
          $ref: '#/components/schemas/DeviceAttribute'
        deviceAtttributeId:
          type: integer
          format: int32
    CustomerDTO:
      type: object
      properties:
        customerId:
          type: integer
          format: int32
        customerName:
          type: string
        description:
          type: string
        phone:
          type: string
        email:
          type: string
        address:
          type: string
        createdDate:
          type: string
          format: date-time
        createdBy:
          type: integer
          format: int32
        updatedDate:
          type: string
          format: date-time
        updatedBy:
          type: integer
          format: int32
    UserCustomerDTO:
      type: object
      properties:
        userId:
          type: integer
          format: int32
        customerId:
          type: integer
          format: int32
        fullname:
          type: string
        userEmail:
          type: string
        phone:
          type: string
        description:
          type: string
        createdDate:
          type: string
        createdBy:
          type: integer
          format: int32
        updatedDate:
          type: string
    RequestModel:
      type: object
      properties:
        from:
          type: string
        to:
          type: string
        tokenId:
          type: string
        authorization:
          type: string
        content:
          type: object
        requestIdentifier:
          type: string
        operation:
          type: integer
          format: int32
        method:
          type: string
        headers:
          type: object
          additionalProperties:
            type: string
        queryStrings:
          type: object
          additionalProperties:
            type: array
            items:
              type: string
