public class CharacterController : MonoBehaviour {
	
	//Module level variables
	public float speed = 1.0f;
	public string axisHorizontal = "Horizontal";
	public string axisVertical = "Vertical";
	public Animator anim;
	
	// Use this for initialization
	void Start () {
		anim = gameObject.GetComponent<Animator> ();	
	}
	
	
	
	
	// Update is called once per frame
	void Update () {
		anim.SetFloat("Speed", Mathf.Abs(Input.GetAxis(axisHorizontal)));
		anim.SetFloat("Speed", Mathf.Abs(Input.GetAxis(axisVertical)));
		if (Input.GetAxis (axisHorizontal) < 0)
		{
			Vector3 newScale = transform.localScale;
			newScale.y = 1.0f;
			newScale.x = 1.0f;
			transform.localScale = newScale;
		} 
		else if (Input.GetAxis (axisHorizontal) > 0)
		{
			Vector3 newScale =transform.localScale;
			newScale.x = 1.0f;
			transform.localScale = newScale;        
		}
		
		if (Input.GetAxis (axisVertical) < 0)
		{
			Vector3 newScale = transform.localScale;
			newScale.y = 1.0f;
			newScale.x = 1.0f;
			transform.localScale = newScale;
		} 
		else if (Input.GetAxis (axisVertical) > 0)
		{
			Vector3 newScale =transform.localScale;
			newScale.x = 1.0f;
			transform.localScale = newScale;        
		}
		
		transform.position += transform.right *Input.GetAxis(axisHorizontal)* speed * Time.deltaTime;
		transform.position += transform.up *Input.GetAxis(axisVertical)* speed * Time.deltaTime;
		
	}
	
	
	
	
}
